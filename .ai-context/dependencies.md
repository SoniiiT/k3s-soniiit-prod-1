# Dependencies

| Dependency | Role | Evidence |
| --- | --- | --- |
| K3s/Kubernetes | Runtime cluster and API | Repository description and Kubernetes resources |
| Helm | Service installation and upgrades | All service `install.md` files |
| Traefik | Ingress controller, TLS entry points, middleware, CRDs | `Traefik/`, `Traefik-Ingress/` |
| cert-manager | Certificate and issuer lifecycle | `Cert-Manager/`, route certificate resources |
| Cloudflare | Let's Encrypt DNS01 solver | `Cert-Manager/issuer/cloudflare+letsencrypt/` |
| Longhorn | Persistent storage and NFS backup target | `Longhorn/` |
| Vault | Secret storage and Kubernetes authentication | `Vault/`, `Kestra/` |
| Kestra | Workflow execution and Vault-backed secrets | `Kestra/` |
| PostgreSQL and MinIO | Kestra chart backends | `Kestra/kestra-values.yaml` |
| Argo CD | GitOps/CD controller | `Argo-CD/deployment.yaml` |
| Authentik | Identity provider/service | `Authentik/` |
| CrowdSec | Traefik security signal and bouncer | `Crowdsec/`, `Traefik/middleware/Crowdsec/` |
| Homepage | Cluster/service dashboard | `Homepage/` |
| Portainer | Kubernetes management UI | `Portainer/` |
| kube-prometheus-stack | Prometheus, Grafana, Alertmanager and exporters | `kube-prometheus-stack/` |
| Renovate | Automated YAML/Helm dependency updates | `renovate.json` |

Versions are unevenly pinned: some installation commands pin chart versions, while others use chart defaults and Kestra uses the `latest` image tag. Treat upgrades as deployment changes requiring review.
