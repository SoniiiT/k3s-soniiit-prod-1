# Removing a platform service

1. Confirm ownership and dependencies in the service values, install notes, routes, certificates, middleware, monitoring, Homepage, Argo CD, and Vault.
2. Stop or migrate workloads and persistent data according to the service's operator/chart guidance.
3. Remove service-local resources before shared controllers, issuers, storage, or middleware.
4. Preserve shared resources still referenced by another service.
5. Record any external DNS, load balancer, backup, or data cleanup required; do not delete production data implicitly.
