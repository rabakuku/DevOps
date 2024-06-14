# 1_Installing-Jenkins

##### For more: [Installing Jenkins](https://www.jenkins.io/doc/book/installing/)

### Installing Jenkins on Ubuntu 20.04

#### Prerequisites

Minimum hardware requirements:

<div class="sectionbody" id="bkmrk-256-mb-of-ram-1-gb-o"><div class="ulist">- 256 MB of RAM
- 1 GB of drive space (although 10 GB is a recommended minimum if running Jenkins as a Docker container)

</div></div>Recommended hardware configuration for a small team:

<div class="sectionbody" id="bkmrk-4-gb%2B-of-ram-50-gb%2B-"><div class="ulist">- 4 GB+ of RAM
- 50 GB+ of drive space

</div></div>Comprehensive hardware recommendations:

<div class="sectionbody" id="bkmrk-hardware%3A-see-the-ha"><div class="ulist">- Hardware: see the [Hardware Recommendations](https://www.jenkins.io/doc/book/scaling/hardware-recommendations) page

</div></div>```
sudo apt update -y

#install prerequisite aka JAVA LAVA
sudo apt install fontconfig openjdk-17-jre
java -version


#install Jenkins
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

### Installing Jenkins on Docker   


#### Prerequisites

Minimum hardware requirements:

<div class="sectionbody" id="bkmrk-256-mb-of-ram-1-gb-o-1"><div class="ulist">- 256 MB of RAM
- 1 GB of drive space (although 10 GB is a recommended minimum if running Jenkins as a Docker container)

</div></div>Recommended hardware configuration for a small team:

<div class="sectionbody" id="bkmrk-4-gb%2B-of-ram-50-gb%2B--1"><div class="ulist">- 4 GB+ of RAM
- 50 GB+ of drive space

</div></div>Comprehensive hardware recommendations:

<div class="sectionbody" id="bkmrk-hardware%3A-see-the-ha-1"><div class="ulist">- Hardware: see the [Hardware Recommendations](https://www.jenkins.io/doc/book/scaling/hardware-recommendations) page

</div></div>```
#To use the latest LTS:
docker pull jenkins/jenkins:lts-jdk17

#To use the latest weekly: 
docker pull jenkins/jenkins:jdk17

```

### Setup Jenkins

After Jenkins is up and running to to https://localhost.com:8080

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/WeQORgFXfZebGyke-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/WeQORgFXfZebGyke-image.png)

#### Unlock Jenkins

```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```