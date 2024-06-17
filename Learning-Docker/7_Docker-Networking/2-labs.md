# 2_LABS

### LAB-1

Explore the current setup and identify the number of networks that exist on this system.

```
docker network ls
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/lUdxWA1j7K65Vikm-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/lUdxWA1j7K65Vikm-image.png)

### LAB-2

What is the ID associated with the bridge network?

```
docker network ls
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/lUdxWA1j7K65Vikm-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/lUdxWA1j7K65Vikm-image.png)

### LAB-3

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/o2WwcaPviVIyuoYr-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/o2WwcaPviVIyuoYr-image.png)

```
docker inspect alpine-1
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/BlV2kfxNhBamPblK-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/BlV2kfxNhBamPblK-image.png)

```
docker network ls
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/9dxUhzhKr0h0nvo8-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/9dxUhzhKr0h0nvo8-image.png)

### LAB-4

Run a container named alpine-2 using the alpine image and attach it to the none network.

```
docker run --network=none -d --name=alpine-2 alpine
```

### LAB-5

Create a new network named wp-mysql-network using the bridge driver. Allocate subnet 182.18.0.1/24. Configure Gateway 182.18.0.1

```
docker network create --driver bridge --subnet 182.18.0.1/24 --gateway 182.18.0.1 wp-mysql-network
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/RhxJTodAaVeowdjh-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/RhxJTodAaVeowdjh-image.png)

### LAB-6

Deploy a `mysql` database using the `mysql:5.6` image and name it `mysql-db`. Attach it to the newly created network `wp-mysql-network`

Set the database password to use `db_pass123`. The environment variable to set is `MYSQL_ROOT_PASSWORD`.

```
docker run -d --network=wp-mysql-network -e MYSQL_ROOT_PASSWORD=db_pass123 --name=mysql-db mysql:5.6
```

### LAB-7

Deploy a web application named `webapp` using the `kodekloud/simple-webapp-mysql` image. Expose the port to 38080 on the host.

  
The application makes use of two environment variable:  
1: `DB_Host` with the value `mysql-db`.   
2: `DB_Password` with the value `db_pass123`.  
Make sure to attach it to the newly created network called `wp-mysql-network`.

Also make sure to link the `MySQL` and the `webapp` container.

```
docker run -d --network=wp-mysql-network -p 38080:3306 -e DB_Host=mysql-db -e-DB_Password=db_pass123 --name=webapp kodekloud/simple-webapp-mysql 
```