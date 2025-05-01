helm repo add bitnami https://charts.bitnami.com/bitnami
helm install my-rabbitmq bitnami/rabbitmq --version 15.1.0 --values=rabbitmq-values.yaml -n rabbitmq --create-namespace
