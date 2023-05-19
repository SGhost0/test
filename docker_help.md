## 获取镜像
### docker pull [选项] [Docker Registry 地址[:端口号]/]仓库名[:标签]
docker pull ubuntu:18.04

## 运行镜像
docker run -it --rm ubuntu:18.04 bash  
###### `-it`:这是两个参数，一个是‘-i’:交互式操作，一个是'-t'终端。我们这里打算进入bash执行一些命令并查看返回结果，因此我们需要交互式终端。  
`--rm`:这个参数是说容器退出后随之将其删除。默认情况下，为了排障需求，退出的容器并不会立即删除，除非手动执行docker rm。


