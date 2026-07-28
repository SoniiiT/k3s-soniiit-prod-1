# Project map

## Shape

This is a GitOps-style configuration repository for a production K3s/Kubernetes cluster. It contains Helm values, installation notes, Kubernetes resources, Traefik CRDs, and a large upstream Argo CD manifest. It is not an application source tree and has no local build or test runner.

## Top-level areas

| Area | Purpose |
| --- | --- |
| `Argo-CD/` | Argo CD installation manifest plus image-updater registry configuration |
| `Authentik/` | Authentik Helm values, installation, and public TLS ingress |
| `Cert-Manager/` | cert-manager values, self-signed CA/issuers, and Cloudflare DNS01 issuers |
| `Crowdsec/` | CrowdSec Helm values and installation |
| `Homepage/` | Homepage Helm values, installation, and dashboard ingress |
| `Kestra/` | Kestra Helm values, Vault configuration, flow example, and secret manifests |
| `kube-prometheus-stack/` | Prometheus Operator stack values, ingress routes, and installation |
| `Longhorn/` | Longhorn storage values and node preparation/install notes |
| `Portainer/` | Portainer Helm values and installation |
| `Traefik/` | Traefik Helm values, middleware, and installation |
| `Traefik-Ingress/` | IngressRoute resources grouped by Kubernetes, Home, Docker server, and LXC targets |
| `Vault/` | Vault Helm values and Kubernetes-auth RBAC resources |
| `renovate.json` | Renovate rules for Kubernetes and Helm updates |

## Navigation

- Start with `README.md` for repository purpose and Renovate usage.
- Use each service directory's `install.md` and `*-values.yaml` together.
- Use `Traefik-Ingress/` for service exposure; the service Helm values often only define a backend.
- Use `Cert-Manager/` to trace certificate issuer and secret dependencies.
- Use `Vault/` and `Kestra/` together for the Kestra-to-Vault path.
- Treat files under paths containing `secret`, `credential`, `token`, `key`, `.crt`, or `.clientSecret` as sensitive; inspect them only with explicit authorization.

## Entry points

- Helm installation commands in the service `install.md` files.
- Kubernetes resource application for YAML manifests, typically via `kubectl apply`.
- Traefik `IngressRoute` CRDs are the main routing entry point.
- `Argo-CD/deployment.yaml` is an upstream-style installation bundle rather than hand-written application code.
