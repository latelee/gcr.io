# gcr.io
[![Build Status](https://www.travis-ci.org/latelee/gcrsync.svg?branch=master)](https://www.travis-ci.org/latelee/gcrsync)

all of the gcr.io docker image mirror

# gcr.io  

### 仓库说明
gcr(Google Container Registry)同步仓库列表。  

同步后的镜像文件位于dockerhub的[gcrcontainer](https://hub.docker.com/r/gcrcontainer/)账号中。  

本仓库由[travis-ci](https://www.travis-ci.org/latelee/gcrsync)每天自动定时构建（以保证尽量与gcr同步）。  

同步工具源码位于[latelee/gcrsync](https://github.com/latelee/gcrsync)。感谢原作者[mritd](https://github.com/mritd)提供源码。  

### 命令空间
gcr.io有许多不同的命名空间，对应本仓库相应目录，如`gcr.io/google-containers`对应`google-containers`目录，根据`README.md`或`ImageList`查看具体镜像名称。  

gcr.io的镜像与[https://hub.docker.com/r/gcrcontainer/](https://hub.docker.com/r/gcrcontainer/)一一对应。如镜像`gcr.io/google-containers/pause-amd64:3.0`对应`gcrcontainer/pause-amd64:3.0`。(注意，目前未考虑到不同命名空间镜像重名情况)    


实际中拉取如下镜像：  
```
docker pull gcr.io/google-containers/pause-amd64:3.0
```
等效于：  
```
docker pull gcrcontainer/pause-amd64:3.0
```
对应某些场合必须使用gcr.io前缀的，可用`docker tag`命令达到目的，示例如下：  
```
docker tag gcrcontainer/pause-amd64:3.0 gcr.io/google-containers/pause-amd64:3.0
```
