# anatomy.md

> Auto-maintained by OpenWolf. Last scanned: 2026-09-21T16:32:35.938Z
> Files: 95 tracked | Anatomy hits: 0 | Misses: 0

> Project structure index. Auto-maintained by OpenWolf hooks and daemon.
> Run `openwolf scan` to generate, or wait for the first Claude Code session.
> Status: Pending initial scan

## ./

- `.gitignore` — Git ignore rules (~112 tok)
- `AGENTS.md` — Agent context (~183 tok)
- `CLAUDE.md` — OpenWolf (~190 tok)
- `README.md` — Project documentation (~520 tok)
- `renovate.json` (~277 tok)

## .ai-context/

- `architecture.md` — Architecture (~776 tok)
- `conventions.md` — Conventions (~471 tok)
- `dependencies.md` — Dependencies (~385 tok)
- `manifest.json` (~275 tok)
- `project-map.md` — Project map (~577 tok)

## .ai-context/indexes/

- `files.json` (~1527 tok)
- `symbols.json` (~551 tok)

## .ai-context/knowledge/

- `README.md` — Project documentation (~172 tok)

## .ai-context/knowledge/business-rules/

- `index.md` — Business rules (~70 tok)

## .ai-context/knowledge/decisions/

- `index.md` — Decisions (~47 tok)

## .ai-context/knowledge/feature-guides/

- `ingress-routing.md` — Ingress routing (~282 tok)
- `observability.md` — Observability (~255 tok)
- `platform-services.md` — Platform services (~182 tok)
- `vault-kestra-secrets.md` — Vault and Kestra secrets (~286 tok)

## .ai-context/knowledge/removal-guides/

- `ingress-route.md` — Removing an ingress route (~125 tok)
- `platform-service.md` — Removing a platform service (~141 tok)
- `vault-kestra.md` — Removing Vault/Kestra integration (~140 tok)

## .ai-context/knowledge/risks/

- `index.md` — Risks and uncertainty (~332 tok)

## .github/

- `copilot-instructions.md` — Copilot instructions (~85 tok)

## Argo-CD/authentik/

- `oidc.authentik.clientSecret` (~4 tok)
- `oidc.config` (~74 tok)
- `policy.csv` (~12 tok)

## Argo-CD/registries/

- `registries.yaml` — K8s ConfigMap: argocd-image-updater-config (~117 tok)

## Authentik/

- `authentik-values.yaml` — Declares name (~218 tok)
- `ingress.yaml` — K8s IngressRoute: authentik (~189 tok)
- `install.md` (~56 tok)

## Cert-Manager/

- `cert-manager-values.yaml` (~62 tok)
- `install.md` (~53 tok)

## Cert-Manager/certificates/cloudflare+letsencrypt/

- `certificates-production.yaml` — K8s Certificate: soniiit-net-production (~88 tok)
- `certificates-staging.yaml` — K8s Certificate: soniiit-net-staging (~86 tok)

## Cert-Manager/certificates/selfsigned/

- `certificates-selfsigned-demo.yaml` — K8s Certificate: demo-soniiit-net-selfsigned (~86 tok)
- `certificates-selfsigned-dev.yaml` — K8s Certificate: dev-soniiit-net-selfsigned (~85 tok)
- `certificates-selfsigned-home.yaml` — K8s Certificate: home-soniiit-net-selfsigned (~86 tok)

## Cert-Manager/issuer/cloudflare+letsencrypt/

- `letsencrypt-production.yaml` — K8s ClusterIssuer: letsencrypt-production (~146 tok)
- `letsencrypt-staging.yaml` — K8s ClusterIssuer: letsencrypt-staging (~146 tok)

## Cert-Manager/issuer/selfsigned/demo/

- `ca.crt` (~18 tok)
- `clusterissuer-selfsigned-demo.yml` — K8s ClusterIssuer: selfsigned-issuer-demo (~40 tok)
- `selfsigned-ca-demo.yaml` — K8s Secret: selfsigned-ca-demo (~57 tok)

## Cert-Manager/issuer/selfsigned/dev/

- `ca.crt` (~18 tok)
- `clusterissuer-selfsigned-dev.yml` — K8s ClusterIssuer: selfsigned-issuer-dev (~39 tok)
- `selfsigned-ca-dev.yaml` — K8s Secret: selfsigned-ca-dev (~57 tok)

## Cert-Manager/issuer/selfsigned/home/

- `ca.crt` (~18 tok)
- `clusterissuer-selfsigned-home.yml` — K8s ClusterIssuer: selfsigned-issuer-home (~40 tok)
- `selfsigned-ca-home.yaml` — K8s Secret: selfsigned-ca-home (~58 tok)

## Crowdsec/

- `crowdsec-values.yaml` — for raw logs format: json or cri (docker|containerd) (~205 tok)
- `install.md` (~45 tok)

## Homepage/

- `homepage-values.yaml` (~2747 tok)
- `ingress.yaml` — K8s IngressRoute: homepage (~193 tok)
- `install.md` (~46 tok)

## Kestra/

- `kestra-values.yaml` — ## Image (~3075 tok)
- `vault-config.yaml` — K8s ServiceAccount: kestra-vault (~386 tok)

## Kestra/flows/

- `vault-ssh-key.yaml` (~886 tok)

## Kestra/secrets/

- `ssh-key.yaml` — K8s Secret: ssh-key (~49 tok)
- `tf-id-token.yaml` — K8s Secret: tf-id-token (~52 tok)
- `tf-pve-api-token.yaml` — K8s Secret: tf-pve-api-token (~56 tok)
- `tg-api-token.yaml` — K8s Secret: tg-api-token (~53 tok)
- `tsig-key.yaml` — K8s Secret: tsig-key (~50 tok)

## Longhorn/

- `install.md` (~154 tok)
- `longhorn-values.yaml` (~29 tok)

## Portainer/

- `install.md` (~48 tok)
- `portainer-values.yaml` — Default values for portainer. (~278 tok)

## Traefik-Ingress/Internal/Docker-SRV-01/

- `homepage.yaml` — K8s Service: homepage (~470 tok)
- `kestra.yaml` — K8s Service: kestra (~463 tok)

## Traefik-Ingress/Internal/Docker-SRV-02/

- `n8n.yaml` — K8s Service: n8n (~454 tok)

## Traefik-Ingress/Internal/Home/

- `jellyfin-vue.yaml` — K8s Service: jellyfin-vue (~482 tok)
- `jellyfin.yaml` — K8s Service: jellyfin (~470 tok)
- `jellyseerr.yaml` — K8s Service: jellyseerr (~476 tok)
- `pbs.yaml` — K8s Service: pbs (~454 tok)
- `prowlarr.yaml` — K8s Service: prowlarr (~470 tok)
- `proxmox.yaml` — K8s Service: proxmox (~467 tok)
- `radarr.yaml` — K8s Service: radarr (~464 tok)
- `sonarr.yaml` — K8s Service: sonarr (~464 tok)
- `truenas.yaml` — K8s Service: truenas (~464 tok)

## Traefik-Ingress/Internal/Kubernetes/

- `argocd.yaml` — K8s IngressRoute: argocd-http (~432 tok)
- `longhorn.yaml` — K8s IngressRoute: longhorn-http (~380 tok)
- `traefik.yaml` — K8s IngressRoute: traefik-http (~404 tok)

## Traefik-Ingress/Internal/LXC/

- `checkmk.yaml` — K8s Service: checkmk (~565 tok)
- `pihole.yaml` — K8s Service: pihole (~556 tok)
- `wazuh.yaml` — K8s Service: wazuh (~460 tok)

## Traefik/

- `install.md` (~44 tok)
- `traefik-values.yaml` — Declares for (~873 tok)

## Traefik/middleware/

- `default-headers.yaml` — K8s Middleware: default-headers (~236 tok)
- `middleware.yaml` — K8s Middleware: traefik-dashboard-basicauth (~48 tok)

## Traefik/middleware/Crowdsec/

- `bouncer-middleware.yaml` — K8s Middleware: bouncer (~94 tok)

## Vault/

- `kestra-vault-sa.yaml` — K8s ServiceAccount: kestra-vault (~25 tok)
- `vault-auth.yaml` — K8s ServiceAccount: vault-auth (~106 tok)
- `vault-values.yaml` (~91 tok)

## kube-prometheus-stack/

- `install.md` (~60 tok)
- `kube-prometheus-stack.yaml` — K8s IngressRoute: grafana-ingress (~510 tok)
- `values.yaml` (~1098 tok)
