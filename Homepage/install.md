helm repo add jameswynn https://jameswynn.github.io/helm-charts
helm install homepage jameswynn/homepage --values homepage-values.yaml --create-namespace -n homepage --version 2.0.1
