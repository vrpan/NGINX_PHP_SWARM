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
### Logs

In logs folder You can find acces.log, error.log, php.log
