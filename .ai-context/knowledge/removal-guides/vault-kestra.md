# Removing Vault/Kestra integration

1. Search Kestra values and flows for Vault variables, paths, templates, and the `kestra-vault` service account.
2. Migrate or revoke secrets and Kubernetes auth roles before deleting configuration.
3. Remove the Kestra Vault service account, Role/RoleBinding, ConfigMaps, and unused Vault paths only after dependents are gone.
4. Replace the Kestra datasource configuration and validate all deployments and flows.
5. Keep rollback material for both Vault auth and Kestra configuration through the compatibility window.
