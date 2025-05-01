helm repo add nextcloud https://nextcloud.github.io/helm/
helm install nextcloud nextcloud/nextcloud --version 6.2.4 --namespace nextcloud --create-namespace --set nextcloud.password=changeme,nextcloud.host=127.0.0.1,service.type=ClusterIP,mariadb.enabled=false,externalDatabase.user=nextcloud,externalDatabase.database=nextcloud,externalDatabase.host=YOUR_EXTERNAL_DATABASE_HOST
