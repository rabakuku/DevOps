# 2_LAB

### LAB 1

1\. First create a redis database container called redis, image redis:alpine. if you are unsure, check the hints section for the exact commands.

```
docker run -d --name redis redis:alpine
```

### LAB 2

Next, create a simple container called clickcounter with the image kodekloud/click-counter, link it to the redis container that we created in the previous task and then expose it on the host port 8085. The clickcounter app run on port 5000. if you are unsure, check the hints section for the exact commands.

```
docker run -d --name clickcounter --link redis:redis -p 8085:5000 kodekloud/click-counter
```

### LAB 3  


Let's clean up the actions carried out in previous steps. Delete the redis and the clickcounter containers.

```
docker ps

docker stop 71efa8cbc666
docker stop 5582befab21f

docker rm 71efa8cbc666
docker rm 5582befab21f

docker ps

```

### LAB 4  


Create a `docker-compose.yml` file under the directory `/root/clickcounter`. Once done, run `docker-compose up`.

The compose file should have the exact specification as follows -

<div class="markdown-body text-sm mb-8" id="bkmrk-redis-service-specif">1. `redis` service specification - Image name should be `redis:alpine`.
2. `clickcounter` service specification - Image name should be `kodekloud/click-counter`, app is run on port `5000` and expose it on the host port `8085` in the compose file.

</div>```
vi docker-compose.yml


version: "3"
services:
   redis:
     image: redis:alpine

   clickcounter:
      image: kodekloud/click-counter
      ports:
      - 8085:5000


```

<main class="flex h-full flex-grow justify-center" id="bkmrk-please-click-on-the-">Please click on the links below for further reference:

[https://docs.docker.com/compose/](https://docs.docker.com/compose/)

[https://docs.docker.com/engine/reference/commandline/compose/](https://docs.docker.com/engine/reference/commandline/compose/)

[https://github.com/dockersamples/example-voting-app](https://github.com/dockersamples/example-voting-app)

</main><div class="markdown-body text-sm mb-8" id="bkmrk--1"></div>