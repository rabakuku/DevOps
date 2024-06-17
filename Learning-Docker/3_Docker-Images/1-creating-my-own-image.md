# 1_Creating-My-Own-Image

### Creating My Own Docker Image

#### First, Write down the steps

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/n1NUrQFJUK6pHjMv-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/n1NUrQFJUK6pHjMv-image.png)

#### Create a DockerFile

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/TSfYRP6UZYH6QIHv-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/TSfYRP6UZYH6QIHv-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/xTrcy932eIeTc2cx-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/xTrcy932eIeTc2cx-image.png)

```
#which OS
FROM UBUNTU

#installing the prerequisite
RUN apt-get update
RUN apt-get install python

RUN pip install flask
RUN pip install flask-mysql

#copy source code
COPY ./opt/source-code

#run the app
ENTRYPOINT FLASK_APP=/opt/source-code/app.py flask run

```

#### Build the image  


[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/hdxCCvI8UP6uiIVX-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/hdxCCvI8UP6uiIVX-image.png)

```
#rabakuku is my docker username and the name of the app is my-custom-app
docker build Dockerfile -t rabakuku/mycustomapp
```

#### Publish the image  


```
#rabakuku is my docker username and the name of the app is my-custom-app
docker push rabakuku/my-custom-app
```

#### what can you containerize?

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/iarIQGE4hxjBAVsd-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/iarIQGE4hxjBAVsd-image.png)