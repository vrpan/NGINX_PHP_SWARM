# NGINX_PHP_SWARM
### Clone the repo
### Create Docker image nginx
```
docker build . -t nginx:swarm -f nginx/Dockerfile
```

### Run docker swarm mode
```
docker swarm init 
docker swarm join-token manager
```

### Deploy docker-compose
```
docker stack deploy -c docker-compose.yml test6
```
### Check deployment status
```
docker ps -a
```
The output should be simmilar:
```
CONTAINER ID   IMAGE            COMMAND                  CREATED          STATUS          PORTS      NAMES
71426ebc3d28   nginx:swarm      "/docker-entrypoint.…"   44 seconds ago   Up 42 seconds   80/tcp     test6_nginx.1.dnwiifkdvuh1uczst22j66zzo
0b57854b8327   php:fpm-alpine   "docker-php-entrypoi…"   44 seconds ago   Up 43 seconds   9000/tcp   test6_php.1.397xr408sutfvgqrl9zsawuok
```
### Check connectivity to app
```
curl 127.0.0.1
```
or open in browser address: [NGINX_PHP_SWARM](http://127.0.0.1)
### Logs

In logs folder You can find acces.log, error.log, php.log
