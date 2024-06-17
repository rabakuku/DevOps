# 1_Basic-Docker-Run-Commands

### Docker Run

#### Tags

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/zBdxWsxqsdlRRxIP-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/zBdxWsxqsdlRRxIP-image.png)

```
#To download and run redis version 4.4
#if you do not specify any tags, docker will download the latest
docker run redis:4.0
```

#### Where to find info about Tags

[https://hub.docker.com/](https://hub.docker.com/)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/2gSOXrD8vPa0gGBz-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/2gSOXrD8vPa0gGBz-image.png)

#### STDIN Standard Input

if you would like docker container to take your input, you have to use the -i parameter

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/eHkqIUKBIhy5WE8F-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/eHkqIUKBIhy5WE8F-image.png)

```bash
#interactive with container
docker run -i kodekloud/simple-prompt-docker

#interactive with terminal container
docker run -it kodekloud/simple-prompt-docker
```

#### Port Mapping

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/FxdZGp7390crajFJ-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/FxdZGp7390crajFJ-image.png)

```
#the first port is the host port and the second port is the docker port
docker run -p 80:5000 kodekloud/webapp
```

#### Volume Mapping  


How data is persistent in a docker container. The data will remain even if you delete the docker container because we are mounting the data to the host directory.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/Bnnf55C0nDiOll6Z-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/Bnnf55C0nDiOll6Z-image.png)

```
#the first volume is the host directory and the second volume is the docker directory
docker run -v /opt/datadir:/var/lib/mysql mysql
```

#### Inspect Container

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/gqTJF6KGcmCvEbIF-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/gqTJF6KGcmCvEbIF-image.png)

```
#gets all the information about the docker container in a json format
docker inspect bliss_hopper (ID or Container name)
```

#### Container Logs  


How to view the container logs.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/lwB5AR56VK8l1U7t-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/lwB5AR56VK8l1U7t-image.png)

```
#to see the logs if we ran the docker in a -d detached mode.
docker logs bliss_hopper (ID or Container name)
```