# Architecture

## Deployment shape

The repository describes a single production K3s cluster with Helm-managed platform services and hand-authored Kubernetes resources. Services are exposed through Traefik, persisted with Longhorn where configured, and monitored with kube-prometheus-stack. The repository is declarative, but installation is documented as imperative Helm commands.

## Main flows

### Traffic and TLS

1. Traefik is installed in namespace `traefik` with two replicas and a `LoadBalancer` service at `192.168.178.20`.
2. HTTP and HTTPS use ports 80 and 443; `IngressRoute` resources select the `web` or `websecure` entry point.
3. HTTP routes commonly use a redirect middleware. HTTPS routes select backend services and a TLS secret.
4. cert-manager provisions either self-signed home certificates or Let's Encrypt certificates using Cloudflare DNS01. Certificate resources and route resources must agree on namespace, secret name, issuer, and DNS name.
5. Middleware provides security headers, Traefik dashboard basic auth, and optional CrowdSec bouncer enforcement.

### Platform services

- Argo CD, Authentik, CrowdSec, Homepage, Kestra, Longhorn, Portainer, Vault, and kube-prometheus-stack are installed from Helm charts or upstream manifests.
- `Traefik-Ingress/` exposes internal services on `*.home.soniiit.net`, Docker-host services, LXC services, and selected public services.
- kube-prometheus-stack enables Prometheus, Grafana, Alertmanager, default rules, node exporters, kube-state-metrics, and API/server monitors. Its ingress routes are currently present without active TLS blocks.

### Kestra and Vault

1. Vault is configured with a development server and injector.
2. `Vault/vault-auth.yaml` creates the Kubernetes auth delegator service account and binding.
3. `Vault/kestra-vault-sa.yaml` creates the Kestra service account, a namespace Role with wildcard secret access, and a binding.
4. `Kestra/kestra-values.yaml` configures Kestra deployments to use that service account and points the Vault integration at `https://vault.soniiit.net`.
5. `Kestra/vault-config.yaml` templates PostgreSQL credentials from the Vault `kestra/postgres` path.
6. `Kestra/flows/vault-ssh-key.yaml` demonstrates direct Vault access from Kestra; it is diagnostic/example material and currently prints secret material.

### Update flow

Renovate scans YAML/Helm files daily, groups several platform packages, labels update PRs, disables automerge, and caps hourly/concurrent PRs. There is no local CI workflow or test suite in the repository.

## Boundaries and external systems

- Kubernetes API and K3s nodes are the runtime boundary.
- Helm repositories are external package sources for Traefik, cert-manager, Longhorn, Authentik, Homepage, Portainer, CrowdSec, and Prometheus Community.
- Let's Encrypt and Cloudflare are external certificate services.
- Vault is the secret source for Kestra integration.
- Internal DNS/hosts use `soniiit.net` and `home.soniiit.net`; several routes target Proxmox, TrueNAS, media services, Docker hosts, and LXC services outside this repository.
