helm repo add uptime-kuma https://helm.irsigler.cloud
helm repo update
helm install uptime-kuma uptime-kuma/uptime-kuma --namespace uptimekuma --create-namespace --values=uptimekuma-values.yaml
