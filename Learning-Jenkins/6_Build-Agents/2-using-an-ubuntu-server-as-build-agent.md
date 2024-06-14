# 2_Using-An-Ubuntu-Server-As-Build-Agent

### Ubuntu as a Build Agent

#### For more: [Managing Nodes (jenkins.io)](https://www.jenkins.io/doc/book/managing/nodes/)

### On the Remote Agent

#### Add new user

```
sudo adduser eljefe
```

#### Add eljefe to sudo group

```
sudo usermod -aG sudo eljefe
```

#### Install Java

the only requirement

```
sudo yum install java-11 -y
```

### On the Jenkins Server

#### Install SSH Build Agent

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/4P5on4ps3JWEgAeN-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/4P5on4ps3JWEgAeN-image.png)

#### Create a username and password based credentials

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/NS73f7bxeBGmk1rj-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/NS73f7bxeBGmk1rj-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/nT7jWeWvBDGR0p00-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/nT7jWeWvBDGR0p00-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/MoGP0QM3VLACs6aY-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/MoGP0QM3VLACs6aY-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/7K5ky8Vrr4vT4Zwy-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/7K5ky8Vrr4vT4Zwy-image.png)

#### Go to Manage Jenkins, Manage Credentials

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/jfOnDe1Rujn8nuKq-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/jfOnDe1Rujn8nuKq-image.png)

#### Global Credentials (Unrestricted)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/R43ZnGwa1WSdJFzK-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/R43ZnGwa1WSdJFzK-image.png)

#### Add Credentials

- username: eljefe
- Password: XXXXX

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/pXIlYZR9CQ47NNUU-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/pXIlYZR9CQ47NNUU-image.png)

#### Go to Manage Nodes and Clouds

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/dLyv8IPYdIx0hyB0-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/dLyv8IPYdIx0hyB0-image.png)

#### New Node

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/3SVd8QnW2SUdNz0j-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/3SVd8QnW2SUdNz0j-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/U0nG8bGmitACojqL-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/U0nG8bGmitACojqL-image.png)

```
/home/eljefe
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/Z9p6aucrB5OsGPzl-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/Z9p6aucrB5OsGPzl-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/1apy6tTGUODzR1Ne-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/1apy6tTGUODzR1Ne-image.png)

#### Save, Open Agent, See Logs

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/6AwEfKZxQDuUwZeT-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/6AwEfKZxQDuUwZeT-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/WZb9s0IZiobcoJ1T-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/WZb9s0IZiobcoJ1T-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/RQ6SYUb8p8bBHQd0-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/RQ6SYUb8p8bBHQd0-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/cPyHAz06Na6Rbvds-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/cPyHAz06Na6Rbvds-image.png)