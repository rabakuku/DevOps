# 1_The-Docker-Registry

### Docker Registry

#### What is the docker registry?

That where all the images are stored. It is a central repository of all docker images.

Lets take a look at the nginx image.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/5nTy1Hxoy9T7I4ka-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/5nTy1Hxoy9T7I4ka-image.png)

#### Private Registry

From dockers perspective, to run a container using an image from a private registry, you first login your private registry using the docker log in command and put your credentials.

Always remember to log in before pulling or pushing to a private registry.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/H1dp7lyDJzDBENHo-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/H1dp7lyDJzDBENHo-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/bBqwv86AUK0BeZAn-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/bBqwv86AUK0BeZAn-image.png)

#### Deploy private registry

how do you push your own image to it? Use the Docker image tag command to tag the image with a private registry URL in it.

```
docker run -d -p 5000 --name registry registry:2

```

In this case, since it is running on the same Docker host, I can use local host semicolon 5000, followed by the image name.

```
docker image tag my-image localhost:5000/my-image
```

 I can push my image to my local private registry using the command Docker push and the new image name with the docker registry information int it.

```
docker push localhost:5000/my-image
```

From there on, I can pull my image from anywhere within this network using either local hosts if you are on the same host or the IP of domain name of my docker host if I am accessing form host in my environment.

```
docker pull localhost:5000/my-image
```

```
docker pull 192.168.56.100:5000/my-image
```