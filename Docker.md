### Docker Overview
Docker is a container management service. The keywords of Docker are develop, ship and run anywhere. The whole idea of Docker is for developers to easily develop applications, ship them into containers which can then be deployed anywhere.

- [x] How to start docker service 
```
systemctl start docker
```
- [x] How to check docker service status
```
systemctl status docker
```
- [x] How to check docker version
```
docker version
```
- [x] How to check more information about docker 
```
docker info
```
- [x] How to check network details associated with docker
```
ifconfig -a
```
- [x] How to check all images available
```
docker images
docker images ls
```
- [x] How to check  all containers available
```
docker ps 
docker container ls
```
- [x] How to check all container network available 
```
docker network ls
```
- [x] How to check docker volume available 
```
docker volume ls
```

- [x] How to create a container
```
docker run <imagename>
```
- [x] How to pull an image
```
docker pull <imagename>
```
- [x] how to search an image on dockerhub
```
docker search <imagename>
```
- [ ] Delete container after you stop
```
docker run -
```
- [ ] docker system
```
Commands:
  df          Show docker disk usage
  events      Get real time events from the server
  info        Display system-wide information
  prune       Remove unused data
```
- [x] docker containers
```
 Commands:
  attach      Attach to a running container
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes on a container's filesystem
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  inspect     Display detailed information on one or more containers
  kill        Kill one or more running containers
  logs        Fetch the logs of a container
  ls          List containers
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  prune       Remove all stopped containers
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  run         Run a command in a new container
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  wait        Block until one or more containers stop, then print their exit codes
```

- How to save an image in tar file
```
docker save <image name> >filename.tar
```

- [ ] How to load an existing an image
```
docker load <tar file>
```

docker import file.tar newimage



### Explanation about Load /Save import/export and commmit

- ***save*** works with Docker images. It saves everything needed to build a container from scratch. Use this command if you want to share an image with others.

- ***load*** works with Docker images. Use this command if you want to run an image exported with save. Unlike pull, which requires connecting to a Docker registry, load can import from anywhere (e.g. a file system, URLs).

- ***export*** works with Docker containers, and it exports a snapshot of the container’s file system. Use this command if you want to share or back up the result of building an image.

- ***import*** works with the file system of an exported container, and it imports it as a Docker image. Use this command if you have an exported file system you want to explore or use as a layer for a new image.
