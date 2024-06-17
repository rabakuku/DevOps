# 1_Config-Environment-Variables

### Environment Variables

ENV variables store values such as secrets, API keys, and database URLs. Unlike ARG s, they persist inside the image and the containers created from that template. Users can override ENV values in the command line or provide new values in an ENV file.

#### Usage

If you have an app that you can change the background color, you will have to repackage and create a new image.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/41WkdxOeS9zZFbHW-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/41WkdxOeS9zZFbHW-image.png)

If you want to do it without having to recreate the image, you can pass a ENV or Environment Variables like below APP\_COLOR.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/hANrpicCOVBLBTIp-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/hANrpicCOVBLBTIp-image.png)

next time you run and change the color like below

```
docker run -e APP_COLOR=blue simple-webapp-color
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/Dk7rPMk4wZJRfMO4-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/Dk7rPMk4wZJRfMO4-image.png)

#### How to find Environment Variables on a Docker container that is already running?

```bash
docker inspect blissful_hopper
```

under the "config" you will find the variables

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/5ql3EZULe4x0XKdr-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/5ql3EZULe4x0XKdr-image.png)

#### LAB-1:

Run a container named blue-app using image kodekloud/simple-webapp and set the environment variable APP\_COLOR to blue. Make the application available on port 38282 on the host. The application listens on port 8080.

```bash
docker run -d -p 38282:8080 --name blue-app -e APP_COLOR=blue kodekloud/simple-webapp
```

#### LAB-2:

Deploy a mysql database using the mysql image and name it mysql-db. Set the database password to use db\_pass123. Lookup the mysql image on Docker Hub and identify the correct environment variable to use for setting the root password.

```
docker run -d  --name mysql-db -e MYSQL_ROOT_PASSWORD=db_pass123 mysql 
```