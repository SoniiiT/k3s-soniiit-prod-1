# Removing an ingress route

1. Identify all HTTP, HTTPS, certificate, middleware, and backend references for the host.
2. Confirm the target service is no longer needed outside this repository.
3. Remove route and certificate resources together, preserving shared middleware and shared TLS secrets still referenced elsewhere.
4. Remove corresponding Homepage links or dashboard entries.
5. Verify DNS, Traefik access logs, and the resulting Kubernetes resources before deleting shared components.
