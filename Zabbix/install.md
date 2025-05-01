helm repo add zabbix-community https://zabbix-community.github.io/helm-zabbix/
helm repo update
helm upgrade --install zabbix zabbix-community/zabbix --dependency-update --create-namespace --version 6.1.1 --values=zabbix-values.yaml -n zabbix
