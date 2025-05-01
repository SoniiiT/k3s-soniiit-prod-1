helm repo add gitlab http://charts.gitlab.io/
helm install my-gitlab gitlab/gitlab --version 8.6.1 --values gitlab-values.yaml --namespace gitlab --create-namespace
