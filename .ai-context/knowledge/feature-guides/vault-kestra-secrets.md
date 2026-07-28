# Vault and Kestra secrets

## Surfaces

- Vault chart values: `Vault/vault-values.yaml`
- Kubernetes auth delegation: `Vault/vault-auth.yaml`
- Kestra service account/RBAC and Vault template: `Vault/kestra-vault-sa.yaml`, `Kestra/vault-config.yaml`
- Kestra deployment configuration: `Kestra/kestra-values.yaml`
- Example flow: `Kestra/flows/vault-ssh-key.yaml`

## Dependencies and invariants

- Kestra deployments use the `kestra-vault` service account in namespace `kestra`.
- Vault Kubernetes auth role/path and the service-account binding must agree.
- The Vault path and keys referenced by templates must exist before Kestra starts consuming them.
- RBAC is namespace-scoped in the Kestra manifest but currently grants wildcard access to Secrets.

## Change and removal obligations

Before changing or removing this integration, inventory Kestra flows and chart values that reference Vault, revoke or migrate Vault paths and Kubernetes auth roles, remove service accounts/RBAC/config maps, and verify that no workload still depends on the generated secret file. Rollback requires restoring both auth configuration and the template path.
