`docker version`{{execute}}

`docker info`{{execute}}

`docker search busybox`{{execute}}

`docker pull busybox`{{execute}}

`docker run busybox echo 'Learn from a Watopia'`{{execute}}

`docker ps -a`{{execute}}

`docker rm [replace with container id]`{{execute}}

`docker run --help`{{execute}}

`docker run --rm busybox echo 'Learn from a Watopia'`{{execute}}

`docker ps -a`{{execute}}

`docker run -it --name zwift-ngx -p 8080:80 -d nginx`{{execute}}

`curl localhost:8080`{{execute}}

`docker inspect zwift-ngx`{{execute}}

`docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' zwift-ngx`{{execute}}

`docker inspect --format='{{.Config.Image}}' zwift-ngx`{{execute}}

`docker logs zwift-ngx`{{execute}}

`docker exec zwift-ngx ls`{{execute}}

`docker stop zwift-ngx`{{execute}}

`docker start zwift-ngx`{{execute}}

`docker rm -f zwift-ngx`{{execute}}

`docker rm -f zwift-ngx`{{execute}}

`docker history nginx`{{execute}}

`docker stats`{{execute}}