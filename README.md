# Docker-Java

退出所有运行的container

docker kill $(docker ps -q)

-v bind mount a volume -w woring directory in the container

不用在本机安装docker 就可以实现编译运行java文件

docker run -v ${PWD}:/hello -w /hello openjdk:11.0.10-buster javac Hello.java

Multi-stage bilds allow you to define multiple intermediate images or stages

With multi-stage build, the Dockerfile can contain multiple FROM instructions, Each From instruction starts a new stage with new 

build context. You can copy artifacts from a stage to a stage with --from, the artifacts of previous stage not copie over are discarded

onl the final stage is kept, allowing you to include the tools in the intermediate stages without increasing the size of the final image.

Memory and CPU Options in Containers

Control groups -> limit how much resources like CPU time, system memory, or network bandwith containers can use

Important limits for Containers -> The amount of memory available, The number of available CPUs CPU constraints like shates and quotas

docker run -m 200m my-image

## Building Java Applications with Build Tools and Plugins

### Fabric8 Docker Maven Plugin

The fabric8 Docker Maven plugin allows you to build Docker images and manage containers, the plugin communicates directly with the Docker Engine.

### Layered Deployment with Spring Boot

Layers -> Application Dependencies -> Other resources and classes -> Application code -> Most likely to change

reuse the layer that do not change

Spring Boot JAR Structure

BOOT-INF: -classes -lib
META-INF: -MANIFEST.MF
org - Springframework - boot -loader

### Docker Network

Bridge is the default network driver  Create a private local network

Host Removes the isolation between the Docker host and the containers

Overlay Connects multiple Docker engines

Macvlan gives containers a MAC address

None Disables all networking functions in a container.

![Docker Network](https://github.com/ZehuaWang/Docker-Java/blob/main/DOCKERIMG/Screen%20Shot%202022-03-03%20at%206.22.44%20PM.png)

Docker network command options

Create ls inspect connect disconnect rm prune

### Using Docker compose

To manage more than one container at the same time for the same application.

You need: Docker file, YAML configure fule - docker-compose.yml, Manage containers - docker-compose (or docker compose) command.

### Configuring Java Application in Containers

Using environment variables

Passing parameters with ENTRYPOINT and CMD

Mounting external properties files

Overriding Docker Compose configuration files

Spring Boot Configuration Priority

![Docker Network](https://github.com/ZehuaWang/Docker-Java/blob/main/DOCKERIMG/Screen%20Shot%202022-03-03%20at%209.20.15%20PM.png)
