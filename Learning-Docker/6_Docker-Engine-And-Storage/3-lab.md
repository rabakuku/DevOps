# 3_LAB

### LAB-1

Run a mysql container named mysql-db using the mysql image. Set database password to db\_pass123

Note: Remember to run it in the detached mode.

```
docker run -d --name mysql-db -e MYSQL_ROOT_PASSWORD=db_pass123 mysql
```

### LAB-2

Run a mysql container again, but this time map a volume to the container so that the data stored by the container is stored at /opt/data on the host.

Use the same name : mysql-db and same password: db\_pass123 as before. Mysql stores data at /var/lib/mysql inside the container.

```
docker run \
-d --name mysql-db -e MYSQL_ROOT_PASSWORD=db_pass123 --mount type=bind,source=/opt/data,target=/var/lib/mysql mysql

docker run -d --name mysql-db -e MYSQL_ROOT_PASSWORD=db_pass123 -v /opt/data:/var/lin/mysql mysql
```