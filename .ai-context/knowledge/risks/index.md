# Risks and uncertainty

- **Sensitive material tracked:** credential-like files, tokens, client secrets, private keys, certificates, and plaintext values exist in the repository. Values were not copied into the context. Rotate exposed credentials and review repository history before treating the repository as safe to share.
- **Secret leakage in example flow:** `Kestra/flows/vault-ssh-key.yaml` contains commands that print SSH/Vault secret material. Treat it as diagnostic-only and remove or redact before reuse.
- **Broad RBAC:** `Vault/kestra-vault-sa.yaml` grants wildcard verbs on namespace Secrets to the Kestra service account.
- **Development/security defaults:** Vault development mode, Traefik `insecureSkipVerify`, plaintext/default-like chart credentials, and the Kestra `latest` image tag require explicit production review.
- **TLS uncertainty:** monitoring routes use `websecure` but have TLS sections commented out.
- **Version drift:** several Helm installs do not pin chart versions, and upstream manifests are large generated bundles.
- **No automated validation:** no CI, test, or lint workflow was found; YAML/Kubernetes validation is manual unless operators add tooling.
- **External target ownership:** many routes point to Docker, LXC, Proxmox, TrueNAS, and media services outside this repository.
