# 2_LAB-Config-Environment

#### LAB-1:

Run a container named blue-app using image kodekloud/simple-webapp and set the environment variable APP\_COLOR to blue. Make the application available on port 38282 on the host. The application listens on port 8080.

```
docker run -d -p 38282:8080 --name blue-app -e APP_COLOR=blue kodekloud/simple-webapp
```

#### LAB-2:

Deploy a mysql database using the mysql image and name it mysql-db. Set the database password to use db\_pass123. Lookup the mysql image on Docker Hub and identify the correct environment variable to use for setting the root password.

```
docker run -d  --name mysql-db -e MYSQL_ROOT_PASSWORD=db_pass123 mysql
```