## Laradock (Mongo+NGINX+PHP-FPM+MySQL+Elasticsearch) + Symfony 3.4 + TIG-stack

## Installation
1) Clone repository:
```
git clone https://github.com/romalfc/laradock
```
2) Build project with Docker Compose:
```
docker-compose -f docker-compose.my-custom.yml -f docker-compose.tig-stack.yml up --build -d
```
3) Open in browser Grafana Dashboards (user: admin, pass: admin) [http://localhost:3002](http://localhost:3002)

We are ready!

4) To check NGINX and PHP-FPM metrics availability info go to [http://host.docker.internal/nginx_status](http://host.docker.internal/nginx_status) or [http://localhost/status](http://localhost/status).

## Symfony instantiatiation
1) Install dependencies (may take a while...)
```
docker-compose -f docker-compose.my-custom.yml -f docker-compose.tig-stack.yml exec workspace bash -c "cd /var/www/laradock/symfony; composer install; chmod 777 -R var/;"
```
2) Open in browser [http://symfony.test/app.php](http://symfony.test/app.php)
