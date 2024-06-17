# 1_Docker-Compose-Intro

<main class="flex h-full flex-grow justify-center" id="bkmrk-please-click-on-the-">Please click on the links below for further reference:

- [https://docs.docker.com/compose/](https://docs.docker.com/compose/)
- [https://docs.docker.com/engine/reference/commandline/compose/](https://docs.docker.com/engine/reference/commandline/compose/)
- [https://github.com/dockersamples/example-voting-app](https://github.com/dockersamples/example-voting-app)

</main>[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/XgT4NyBknuyhQAfJ-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/XgT4NyBknuyhQAfJ-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/ZCimTAY42q0wtUJk-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/ZCimTAY42q0wtUJk-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/8YnTitD5s53Vjldu-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/8YnTitD5s53Vjldu-image.png)

#### How to setup the app above with docker run

```
docker run -d --names=redis redis
docker run -d --name=db postgress
docker run -d --name=vote -p 5000:80 voting-app
docker run -d --name=vote -p 5001:80 result-app
docker run -d --name=worker -p 5001:80 worker

```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/ZHZ8JlWPh5pjoBpm-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/ZHZ8JlWPh5pjoBpm-image.png)

This is a problem because they cannot communicate with each other because we have not linked them together. if you want to link them together, we have to use --links.

#### docker run --links

```
docker run -d --names=redis redis
docker run -d --name=db postgress
docker run -d --name=vote -p 5000:80 --link redis:redis voting-app
docker run -d --name=vote -p 5001:80 --links db:db result-app
docker run -d --name=worker -p 5001:80 --links db:db --links redis:redis worker

```

the --links creates a host entry so the docker can find it.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/Dt1GLu0h48uUyilb-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/Dt1GLu0h48uUyilb-image.png)

Links is deprecated and it will be removed soon... Which is why we use docker-compose!!

##### Docker compose

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/UZSqebqesETpSs46-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/UZSqebqesETpSs46-image.png)

##### run docker compose file

```
docker-compose up
```

#### Docker compose Build  


for more: [https://sreeninet.wordpress.com/2017/03/28/comparing-docker-compose-versions/](https://sreeninet.wordpress.com/2017/03/28/comparing-docker-compose-versions/)

##### how to tell docker compose to build an image that is not on hub.docker.com or locally available

we will replace the image with build and provide it with the dockerfile location.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/rd7LhVEwkX0WoYwI-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/rd7LhVEwkX0WoYwI-image.png)

#### Docker compose versions  


##### v1

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/ipLQsnHF9NRisNoM-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/ipLQsnHF9NRisNoM-image.png)

##### v2

has: depends-on = which is to specify which the order of docker images startup

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/MXX3BNvZx3eg0HrF-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/MXX3BNvZx3eg0HrF-image.png)

##### v3

if was introduced to add docker swarm.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/O3a3Fb1RJj4Jahjo-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/O3a3Fb1RJj4Jahjo-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/P6D82vJSDrRJHgTk-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/P6D82vJSDrRJHgTk-image.png)

##### Network in Docker compose

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/jzMJjsrkxNGGEulv-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/jzMJjsrkxNGGEulv-image.png)