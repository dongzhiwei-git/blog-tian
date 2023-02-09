---
title: Writing technical content in Markdown
date: 2019-07-12
math: true
image:
  placement: 2
  caption: "Image credit: [**John Moeses
    Bauan**](https://unsplash.com/photos/OGZtQF8iC0g)"
---
# Podman in Docker

​	最近在玩Docker in Docker，水一期Podman in Docker把。我们知道Docker in Docker 一般都是挂载docker.sock文件，这样就造成Docker会高度依赖容器，那有什么构建容器的工具不依赖宿主机呢？这就是我们的主角——Podman



```
#1.用docker起个容器
 docker run -it --privileged -v  ~/dzw/podman/registries.conf:/etc/containers/registries.conf docker.io/dockerhub/test:perf-test  bash
#2.在容器里使用Podman运行容器
podman run --storage-driver=vfs --cgroup-manager=cgroupfs --events-backend=file -id docker.io/dockerhub/test:v2
#注：--privileged是以特权模式运行容器
```

