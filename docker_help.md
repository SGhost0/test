## 获取镜像
docker pull [选项] [Docker Registry 地址[:端口号]/]仓库名[:标签]  
docker pull ubuntu:18.04  


## 查看镜像
docker image ls  
docker image ls -a//查看中间层镜像  
docker system df//查看镜像、容器、数据卷所占用的空间  
docker image ls -f dangling=true//查看虚悬镜像  


## 删除镜像
docker image rm [选项] <镜像1> [<镜像2> ...]  
docker image rm 501//使用短ID删除  
docker image rm centos//使用镜像名删除  


## 运行镜像
docker run -it --rm ubuntu:18.04 bash  
###### `-it`:这是两个参数，一个是`-i`:交互式操作，一个是`-t`终端。我们这里打算进入bash执行一些命令并查看返回结果，因此我们需要交互式终端。
###### `--rm`:这个参数是说容器退出后随之将其删除。默认情况下，为了排障需求，退出的容器并不会立即删除，除非手动执行`docker container rm`。
###### `bash`:放在镜像名后的是命令，这里我们希望有个交互式shell，因此用的是bash。
docker run ubuntu:18.04 /bin/echo 'Hello world'  
docker run -d ubuntu:18.04 /bin/sh -c "while true; do echo hello world; sleep 1; done"  
###### `-d`:指让容器在后台运行并且不把运行的结果打印到宿主机上，但也可以用`docker logs [container id]`查看输出结果。

## 查看容器
docker container ls  
docker container ls -a//查看已终止的容器  


## 启动容器
docker container start ubuntu:18.04  

## 进入容器
docker attach [container id]  
docker exec -it [container id] [command]//推荐使用，退出不会导致容器的终止  
###### `-it`:只用`-i`参数时，由于没有分配伪终端，界面没有我们熟悉的Linux命令提示符，但命令执行结果仍然可以返回。

## 终止容器
docker container stop [container id]  

## 删除容器
docker container rm [container id]  
docker container prune//删除所有处于终止状态的容器  
