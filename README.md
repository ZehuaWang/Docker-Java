# Docker-Java

退出所有运行的container
docker kill $(docker ps -q)

-v bind mount a volume -w woring directory in the container
docker run -v ${PWD}:/hello -w /hello openjdk:11.0.10-buster javac Hello.java
