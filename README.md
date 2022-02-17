# Docker-Java

退出所有运行的container
docker kill $(docker ps -q)

-v bind mount a volume -w woring directory in the container

不用在本机安装docker 就可以实现编译运行java文件

docker run -v ${PWD}:/hello -w /hello openjdk:11.0.10-buster javac Hello.java

Multi-stage bilds allow you to define multiple intermediate images or stages
