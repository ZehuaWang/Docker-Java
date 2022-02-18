# Docker-Java

1. 退出所有运行的container
docker kill $(docker ps -q)

-v bind mount a volume -w woring directory in the container

2. 不用在本机安装docker 就可以实现编译运行java文件

docker run -v ${PWD}:/hello -w /hello openjdk:11.0.10-buster javac Hello.java

3. Multi-stage bilds allow you to define multiple intermediate images or stages

With multi-stage build, the Dockerfile can contain multiple FROM instructions, Each From instruction starts a new stage with new 

build context. You can copy artifacts from a stage to a stage with --from, the artifacts of previous stage not copie over are discarded

onl the final stage is kept, allowing you to include the tools in the intermediate stages without increasing the size of the final image.

4. Memory and CPU Options in Containers

Control groups -> limit how much resources like CPU time, system memory, or network bandwith containers can use

Important limits for Containers -> The amount of memory available, The number of available CPUs CPU constraints like shates and quotas

docker run -m 200m my-image
