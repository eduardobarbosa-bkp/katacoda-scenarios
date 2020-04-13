Provides docker version information
`docker version`{{execute}}

Shows system-wide information
`docker info`{{execute}}
`clear`{{execute}}

Searches the Docker Hub for images
`docker search busybox`{{execute}}

Pulls an image or a repository from your local registry or Docker Hub
`docker pull busybox`{{execute}}

Displays the history of an image
`docker history nginx`{{execute}}

Runs a command in a container
`docker run busybox echo 'Learn from a Watopia'`{{execute}}
`docker run --help`{{execute}}
`docker ps -a`{{execute}}

Runs a command in a container but set a flag to auto remove after execution
`docker run --rm busybox echo 'Learn from a Watopia'`{{execute}}
`docker ps -a`{{execute}}

`clear`{{execute}}

Runs a command in a nginx container setting name and bind host and container port
`docker run -it --name zwift-ngx -p 8080:80 -d nginx`{{execute}}

In a new terminal run
`curl localhost:8080`{{execute}}
`docker stats`{{execute}}


Finds system-level information about docker containers and images
`docker inspect zwift-ngx`{{execute}}
`docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' zwift-ngx`{{execute}}
`docker inspect --format='{{.Config.Image}}' zwift-ngx`{{execute}}

Show the container outuput logs
`docker logs zwift-ngx`{{execute}}
`docker logs zwift-ngx -f`{{execute}}

Runs a command in a container that is active or running
`docker exec zwift-ngx ls`{{execute}}

Stops running containers.
`docker stop zwift-ngx`{{execute}}

Starts already stopped containers.
`docker start zwift-ngx`{{execute}}

Remove containers using force flag
`docker rm -f zwift-ngx`{{execute}}