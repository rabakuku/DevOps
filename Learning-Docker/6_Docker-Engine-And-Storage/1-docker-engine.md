# 1_Docker-Engine

### How docker works?

#### When you installed docker, you installed three different components:

- Docker CLI
- REST API
- Docker Deamon

#### Docker Daemon

Docker Daemon: A persistent background process that manages Docker images, containers, networks, and storage volumes. The Docker daemon constantly listens for Docker API requests and processes them.

#### Docker Engine REST API   


Docker Engine REST API: An API used by applications to interact with the Docker daemon; it can be accessed by an HTTP client.

#### Docker CLI

Docker CLI: A command line interface client for interacting with the Docker daemon. It greatly simplifies how you manage container instances and is one of the key reasons why developers love using Docker.

The docker CLI does not need to be on the same host. It can be on another host and control the docker deamon via the RESTA API

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/suZ2wJvdKzULjcIG-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/suZ2wJvdKzULjcIG-image.png)

#### How to connect to a remote Docker Deamon?

```
docker -H=remote-docker-engine:2375
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/MlOJJp9uXi9Vf9xs-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/MlOJJp9uXi9Vf9xs-image.png)

```
docker -H=remote-docker-engine:2375 run nginx
```

#### NameSpaces

For more: [https://medium.com/@kasunmaduraeng/docker-namespace-and-cgroups-dece27c209c7](https://medium.com/@kasunmaduraeng/docker-namespace-and-cgroups-dece27c209c7)

Docker uses a technology called namespaces to provide the isolated workspace called the container. These namespaces provide a layer of isolation. Each aspect of a container runs in a separate namespace and its access is limited to that namespace.

Namespaces are one of a feature in the Linux Kernel and fundamental aspect of containers on Linux. On the other hand, namespaces provide a layer of isolation. Docker uses namespaces of various kinds to provide the isolation that containers need in order to remain portable and refrain from affecting the remainder of the host system. Each aspect of a container runs in a separate namespace and its access is limited to that namespace.

Namespace Types:

- Process ID
- Mount
- IPC (Interprocess communication)
- User (currently experimental support for)
- Network

#### Common control groups

- CPU
- Memory
- Network Bandwidth
- Disk
- Priority

we could have a lot of flexibility to manage every cgroup according to our requirements.

For example you could see systemd-cgls and systemd-cgtop commands show how cgroup working on the underline host server.

```
    kasunr@~:# $ systemd-cgls
```

##### Control group list

For more: [https://medium.com/@kasunmaduraeng/docker-namespace-and-cgroups-dece27c209c7](https://medium.com/@kasunmaduraeng/docker-namespace-and-cgroups-dece27c209c7)

Using these cgroup policies is very simple. If you for instance want to lock down a Docker container to the first CPU core, you’d append --cpuset-cpus=0 to your docker run command.And also you could setup the cpu shares which you required.

```
$ docker run -d --name='kasun_priority_1' --cpuset-cpus=0 --cpu-shares=20 kasuntest1

$ docker run -d --name='kasun_priority_2' --cpuset-cpus=2 --cpu-shares=30 kasuntest2
```

And we could use the below command to change running container CPU shards.

```
sudo systemctl set-property docker-7d7ds9s7dhdsda044b29cb873cac460b429cfcbdd0e877c0868eb2a901dbf80.scope CPUShares=512
```

In Summary, Namespace gives the isolation for the container with the underline host where Cgroup gives the ability to allocate things to those containers. In my point of view, we would get some understanding and practical experience with namespace and Cgroups in the blog. I will share my more experience with the next post !.