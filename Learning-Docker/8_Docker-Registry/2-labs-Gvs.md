# 2_LABS

### LAB-1

Which command is used for Login to a self-hosted registry?

```
docker login SERVER
```

### LAB-2

Let practice deploying a registry server on our own. Run a registry server with name equals to my-registry using registry:2 image with host port set to 5000, and restart policy set to always.

Note: Registry server is exposed on port 5000 in the image.

Here we are hosting our own registry using the open source Docker Registry.

```
docker run --restart=always -d -p 5000:5000 --name my-registry registry:2
```

### LAB-3

Now its time to push some images to our registry server. Let's push two images for now .i.e. nginx:latest and httpd:latest.

Note: Don't forget to pull them first.

To check the list of images pushed , use curl -X GET localhost:5000/v2/\_catalog

```
#download images
docker pull nginx:latest
docker pull httpd:latest

#tag image
docker image tag nginx:latest localhost:5000/nginx:latest
docker image tag httpd:latest localhost:5000/httpd:latest

#upload image
docker push localhost:5000/nginx:latest
docker push localhost:5000/httpd:latest

#To check the list of images pushed , use 
curl -X GET localhost:5000/v2/_catalog
```

### LAB-4

---

```
#Remove all docker images
docker image prune -a

#To get list of images use
docker image ls
```

### LAB-5

Now we can pull images from our registry-server as well. Use docker pull \[server-addr/image-name\] to pull the images that we pushed earlier.

```
#In our case we can use: 
docker pull localhost:5000/nginx
```

---