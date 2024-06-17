# 2_Demo-Creating-My-Own-Image

### Create Docker Image

#### Run Ubuntu to Test

```
#this will give m interactive mode with ubuntu terminal
docker run -it ubuntu bash

```

#### Installing requirements

```
apt-get update
apt install python -y
apt-get install python-pip
pip install flask-mysql
pip install flask

#download webservice
curl -o /opt/app.py https://raw.githubusercontent.com/mmumshad/simple-webapp-flask/master/app.py

#start the web service
FLASK_APP=/opt/app.py flask run --host=0.0.0.0

#Open a browser and go to URL
http://<IP>:5000                            => Welcome
http://<IP>:5000/how%20are%20you            => I am good, how about you?
```

### How to dockerize it?

#### Create the Dockerfile

```
FROM ubuntu

RUN apt-get update
RUN apt-get install python3 -y
RUN apt-get install python3-flask -y
RUN apt-get install curl -y

#download webservice
RUN curl -o /opt/app.py https://raw.githubusercontent.com/mmumshad/simple-webapp-flask/master/app.py

#start the web service
ENTRYPOINT FLASK_APP=/opt/app.py flask run --host=0.0.0.0
```

#### Build it

```
docker build . -t rabakuku/my-first-webapp
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/KvpQETsjahlTb78x-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/KvpQETsjahlTb78x-image.png)

```
#see that my image it local, but not published on hub.docker.com
docker images
```

```
#run your image
docker run -d rabakuku/my-first-webapp
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/pMc0090ZISYFLKz8-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/pMc0090ZISYFLKz8-image.png)

##### Check the IP to access it

```
#run your image
docker inspect 645436a4395d
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/UeXw559bn7eVBfLt-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/UeXw559bn7eVBfLt-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/WnnzJRMvj7cEmYEy-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/WnnzJRMvj7cEmYEy-image.png)

#### Publish it

##### Create an access token

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/UcsC7AJlEMw8w09z-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/UcsC7AJlEMw8w09z-image.png)

```
docker login -u
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/LNe1XonpVZoSLQ06-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/LNe1XonpVZoSLQ06-image.png)

```
docker push rabakuku/my-first-webapp
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/iGmPapFK9B9LPXDG-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/iGmPapFK9B9LPXDG-image.png)

##### BOOMM!!

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/dCE8xMDQe9qrFF3U-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/dCE8xMDQe9qrFF3U-image.png)

#### Lets Test the Repo

```
#first, remove the docker and local image

docker stop competent_mclean
docker rm competent_mclean
docker rmi rabakuku/my-first-webapp

#now, lets pull to download from docker repo!
docker run -d -p 81:5000 rabakuku/my-first-webapp
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/yevWYSsuRW8ciCVo-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/yevWYSsuRW8ciCVo-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/1d6Lc9AU27W5SaZA-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/1d6Lc9AU27W5SaZA-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/iLf9UH8q1PHaoUgK-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/iLf9UH8q1PHaoUgK-image.png)