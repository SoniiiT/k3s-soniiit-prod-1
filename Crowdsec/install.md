helm repo add crowdsec https://crowdsecurity.github.io/helm-charts
helm repo update
helm install crowdsec crowdsec/crowdsec -n crowdsec -f crowdsec-values.yaml --create-namespace
