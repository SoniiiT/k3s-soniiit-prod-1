# Ingress routing

## Surfaces

- Controller values: `Traefik/traefik-values.yaml`
- Shared middleware: `Traefik/middleware/`
- Route resources: `Traefik-Ingress/Internal/`
- Service-local route resources: `Authentik/ingress.yaml`, `Homepage/ingress.yaml`, and `kube-prometheus-stack/kube-prometheus-stack.yaml`

## Dependencies and invariants

- Traefik CRDs and the `traefik` ingress class must exist before routes are applied.
- Route namespace, backend service name, backend port, host, entry point, middleware namespace, certificate issuer, and TLS secret must remain consistent.
- HTTP redirect routes and HTTPS routes are normally paired.
- External targets in Home, Docker-SRV, and LXC folders are not owned by this repository.

## Change and removal obligations

When adding a service, add the route, certificate if needed, middleware references, and documentation/installation linkage. When removing one, remove both HTTP/HTTPS routes, certificate resources, service-local ingress, and unused middleware only after confirming no other route references them. Check DNS and external service ownership before cleanup.
