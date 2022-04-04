# Docker Zh

Docker 源代码分析，学习路线: Docker 使用 libcontainerd 封装了 Linux API 操作，后期开源了 containerd，Kubernetes 将 Docker 替换为 containerd。containerd 仍存在安全性问题，因为它需要一个进程处于 root 特权模式运行。后来开源世界诞生了 podman，podman 没有守护进程，并且不需要使用 root 特权模式运行。

# 编译

- 安装 Docker Desktop（Windows 或者 Mac 平台）, Linux/Unix 只需要安装 Docker 即可。
- 执行构建命令:

	```shell
	sudo modprobe ip_vs
	docker build --force-rm --build-arg mirrors.tuna.tsinghua.edu.cn -t moby:current .
	```

- 或者在 Linux 主机上直接编译:

	```shell
	mkdir -p $GOATH/src/github.com/moby
	mkdir -p $GOATH/src/github.com/docker
	git clone https://github.com/bluemiaomiao/moby-zh.git $GOATH/src/github.com/moby/moby
	git clone https://github.com/docker/cli.git /$GOPATH/src/github.com/docker/cli
	```
