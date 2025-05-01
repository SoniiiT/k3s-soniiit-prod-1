openssl rand 60 | base64 -w 0

helm repo add authentik https://charts.goauthentik.io
helm repo update
helm upgrade --install authentik authentik/authentik -f authentik-values.yaml --namespace authentik --create-namespace
