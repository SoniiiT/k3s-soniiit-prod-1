helm repo add fmjstudios https://fmjstudios.github.io/helm
helm repo update
helm install my-vaultwarden fmjstudios/vaultwarden --version 0.2.3 -n bitwarden --create-namespace --values=bitwarden-values.yaml
