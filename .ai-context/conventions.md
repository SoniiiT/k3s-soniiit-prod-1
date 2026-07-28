# Conventions

## Repository and YAML

- Use directory-per-service organization and descriptive lowercase or PascalCase file names matching the service.
- Prefer YAML manifests and Helm `values.yaml` files; multi-resource documents use `---`.
- Resource names, namespaces, hostnames, and TLS secret names are explicit.
- Traefik routes use `traefik.io/v1alpha1` `IngressRoute` and `Middleware` resources with `kubernetes.io/ingress.class: traefik`.
- Installation notes use short shell command sequences: add Helm repo, update repo, then install or upgrade with namespace and values.
- Comments and documentation are mixed German and English; preserve the existing language of the file being edited.

## Operational patterns

- Self-signed certificates are scoped to home/dev/demo environments; public certificates use the `soniiit.net` Cloudflare DNS01 issuer.
- Backend services are normally addressed by Kubernetes service name and port from an `IngressRoute`.
- Helm values commonly set resource counts, ingress behavior, service type, persistence, and service-account names.
- Renovate is the dependency-update mechanism; do not assume local package-manager workflows.

## Validation expectations

- No project-native automated test or lint command was found.
- For changes, validate YAML syntax and Kubernetes resource structure with available repository/operator tooling when explicitly requested or available.
- Cross-check namespace, service, issuer, TLS secret, host, and middleware references manually.
- Do not copy secret values into documentation, context, commits, or review output.

## Security conventions and deviations

The repository intends to use Kubernetes Secrets, Vault, cert-manager, and middleware for security, but several tracked files contain secret-like values or sensitive artifacts. Treat that as a risk to remediate, not as a convention to repeat.
