helm repo add teleport https://charts.releases.teleport.dev
helm repo update
helm install teleport teleport/teleport-cluster --namespace teleport-cluster --create-namespace --values=teleport-cluster-values.yaml

kubectl --namespace teleport-cluster exec deployment/teleport-auth -- tctl users add soniiit --roles=access,editor
