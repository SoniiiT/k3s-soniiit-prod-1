helm repo add traefik https://helm.traefik.io/traefik
helm repo update
helm install --namespace=traefik traefik traefik/traefik --create-namespace --values=traefik-values.yaml
