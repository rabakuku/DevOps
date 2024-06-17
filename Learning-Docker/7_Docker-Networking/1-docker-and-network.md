# 1_Docker-and-Network

### Default Networks

When you installed docker, it creates three networks by default, bridge, none, and host.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/3bVwarYJDnOTrssa-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/3bVwarYJDnOTrssa-image.png)

#### How to specify a Network with Docker Run?

```
#bridge
docker run ubuntu

#none
docker run --network=none


#host
docker run --network=host
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/wXZjq9165oY4Mdtn-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/wXZjq9165oY4Mdtn-image.png)

#### Bridge Network

is a private internal network on the host. all containers are attched ti this network by default, and they get an internal IP address usually in the range 172.17.X.X series. The containers can access each other using the internal IP if required. To access any containers from the outside world, map the ports of these containers to ports on the docker host.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/od25lYtKIVRYlper-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/od25lYtKIVRYlper-image.png)

#### Host Network

Another way to access the containers externally is to associate the container to the host network. This takes out any network isolation between docker host and the docker container. Meaning, if you were to run a web server on port 5000 in a web container, it is automatically accessible on the same port externally without requiring any port mapping. This would also mean that unlike before, you will now no be able to run multiple web containers on the same host on the same port, as the ports are now common to all containers in the host network.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/MPCB65hhg6GJN6l4-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/MPCB65hhg6GJN6l4-image.png)

#### None Network

With the none network, the containers are not attached to any network and does not have any access to the external network or other containers; They run isolated network.

### User-Defined Networks

for more: [https://docs.docker.com/reference/cli/docker/network/create/](https://docs.docker.com/reference/cli/docker/network/create/)

So, all containers associated to the default network will be able to communicate to each other. But if we wish to isolate the containers within the Docker host, for example, the first two web containers on internal network 172. and the second two containers on a different internal network like 182... Remember, by default, docker only creates one internal bridge network.

We could create our own internal network using the Docker network command:

```
docker network create \
      --driver bridge \
      --subnet 182.18.0.0/16
      --gateway 182.18.0.1
      custom-isolated-network

#list all networks
docker network ls
```

List all docker networks

```
docker network ls
```

#### Inspect Network of a Container  


```
docker inspect blissfull_hopper
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/0wVKmNysKBJvs72p-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/0wVKmNysKBJvs72p-image.png)

#### Embedded DNS

Containers can reach each other using their names. For example, in this case, I have a web server and MYSQL database container running on the same node. How can I get the web server to access the database on the database container? One thing I could do is to use the internal IP address assigned to the MYSQL container, which, in this case is 172.70.0.3, but that is not very ideal because it is not guaranteed that the container will get the same IP when the system reboots.

The right way to do it is to use the container name. All containers in a docker host file can resolve each other with the name of the container.

Docker has a built-in DNS server that helps the container to resolve each other using the container name.

Built-in DNS server always runs at address 127.0.0.11.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/01btvDyazzTK47tW-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/01btvDyazzTK47tW-image.png)