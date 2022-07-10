## Wordpress 

WordPress is a free and open-source content management system written in PHP and paired with a MySQL or MariaDB database with supported HTTPS.

## Installation

- Apply manifests: `kubectl apply -f .`

```
secret/mysql-pass created
persistentvolumeclaim/mysql-pv-claim created
deployment.apps/wordpress-mysql created
service/wordpress-mysql created
persistentvolumeclaim/wp-pv-claim created
deployment.apps/wordpress created
service/wordpress created
```

## Access Wordpress from GUI
- Get dashboard URL: `minikube service wordpress --url`

## Set port 8080 on Wordpress
- Change the settings on Wordpress: `Setting - Wordpress Address (URL) 127.0.0.1:8080, Site Address (URL) 127.0.0.1:8080`

## Use porto forwarding to access the application
- Use port forwarding: `kubectl port-forward svc/wordpress 8080:80`

## Access the application from the browser
- Access to the admin panel: `http://127.0.0.1:8080/wp-admin`
- Access to the site: `http://127.0.0.1:8080`