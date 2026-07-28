# Platform services

The repository manages Argo CD, Authentik, Homepage, Longhorn, Portainer, Traefik, Vault, Kestra, CrowdSec, cert-manager, and monitoring as independent service areas. Each service normally has a values file and/or installation note; some have a route and certificate resource.

When extending a service, update the service-local values/install resources first, then trace shared dependencies in `Traefik/`, `Cert-Manager/`, `Vault/`, and `Traefik-Ingress/`. Check Renovate matching rules for image/chart update coverage. Do not infer that a service is safe to remove merely because its Helm values are self-contained: routes, TLS secrets, dashboard links, Vault paths, and external targets can be separate.
