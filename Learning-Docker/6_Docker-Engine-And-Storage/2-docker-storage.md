# 2_Docker-Storage

### File System

#### Where does docker stores data in the file system?

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/giz8KiyESnOkCoM5-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/giz8KiyESnOkCoM5-image.png)

### Docker Storage

#### Every time docker creates an image, it saves them in a layer like below

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/MJNXryxM6xPXteYG-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/MJNXryxM6xPXteYG-image.png)

#### COPY ON FILE

You cannot make a change on a docker image. The only way to do it is to change the Dockerfile and rebuild the app. You can make changes to the running container though.

If you get rid of an container, all the data changed or modified gets deleted.... UNLESS UNLESS.. You create a volume and mount it to the host :)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/nxtEYBc7nOmYxgqy-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/nxtEYBc7nOmYxgqy-image.png)

### Volumes

For more: [https://docs.docker.com/storage/volumes/](https://docs.docker.com/storage/volumes/)

#### Docker Data persistent

The command below will create a directory under /var/lib/docker/volumes/data\_volume

```
docker volume create data_volume
```

If you want to mount a docker container using the volume above you can do the following. Even if the container is destroyed, the data stays on the host!!!!! what?????????????

```
#data_volume is the host; /var/lib/mysql is the location I want to safe of the docker container
docker run -v data_volume:/var/lib/mysql mysql
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/KNIw0GHlkfxKD7Qb-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/KNIw0GHlkfxKD7Qb-image.png)

what if you did not run the volume command to create the volume before running the docker container?? You can run the command and docker will create the volume for you bad boi! ;)

```
#data_volume2 is the host; /var/lib/mysql is the location I want to safe of the docker container
docker run -v data_volume2:/var/lib/mysql mysql
```

what if you want to mount the data to another location that is not /var/lib/docker? You can do so by proving the full path of the location... This is also called bind mounting.

```
#/data/mysql is the host; /var/lib/mysql is the location I want to safe of the docker container
docker run -v /data/mysql:/var/lib/mysql mysql

#the new way to do this is by using --mount command
docker run \
--mount type=bind,source=/data/mysql,target=/var/lib/mysql mysql
```

### Storage drivers

For more: [https://docs.docker.com/storage/storagedriver/select-storage-driver/](https://docs.docker.com/storage/storagedriver/select-storage-driver/)

who is in charge of doing the mounting and moving data from container to host???

Ideally, very little data is written to a container's writable layer, and you use Docker volumes to write data. However, some workloads require you to be able to write to the container's writable layer. This is where storage drivers come in.

Docker supports several storage drivers, using a pluggable architecture. The storage driver controls how images and containers are stored and managed on your Docker host. After you have read the storage driver overview, the next step is to choose the best storage driver for your workloads. Use the storage driver with the best overall performance and stability in the most usual scenarios.

Common storage drives:

- AUFS
- ZFS
- BTRFS
- Device Mapper
- Overlay
- Overlay2