# tools_used_by_oto
# openthos编译环境使用
### docker工具包
采用了docker工具将openthos编译所需的工具打包到了下面的文件:  
**openthos_compile_env.tar**
### 使用docker工具包
1.下载openthos_compile_env.tar到本机  
**由于原本的文件2G，超出了github单文件100M的限制，所以在此切分出来**
下载openthos_compile_env下所有文件 
```
cd openthos_compile_env  
cat openthos_docker_* > openthos_compile_env.tar
```
2，安装docker工具(推荐64位系统)  
**apt-get install docker docker.io**  
3.导入工具包
```
docker load < openthos_compile_env.tar  
```
4.查看导入镜像
```
docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
<none>              <none>              230541be7a97        19 minutes ago      2.073 GB
```
5.使用工具包
```
创建容器:
docker run -it -v /home/oto/largeHD/work:/root/oto --name oto-5.1 230541be7a97 /bin/bash
/home/oto/largeHD/work：local工作路径
/root/oto：local工作路径在docker中的映射路径
oto-5.1:container name
8a5f82246607:在docker images中看到的image id

启动容器:
docker start -ai oto-5.1
```
