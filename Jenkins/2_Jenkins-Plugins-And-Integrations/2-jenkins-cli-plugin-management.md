# 2_Jenkins-CLI-plugin-management

##### For More: [Jenkins CLI](https://www.jenkins.io/doc/book/managing/cli/)

```sh
java -jar jenkins-cli.jar -s http://localhost:8085 -auth 'admin:Adm!n321' <command>
```

Notes:  
**1.** You might need to restart Jenkins service after installing some plugins or after making some configuration changes etc. In such case please make sure Jenkins service is back up before you submit your solution.  
**2.** Please make a note of Jenkins credentials given above.  
**3.** This lab is mainly focused on Jenkins CLI so please avoid using Jenkins UI during this lab.

### list-plugins

```
java -jar jenkins-cli.jar -s http://localhost:8085 -auth 'admin:Adm!n321' list-plugins
```

### install-plugin

```
java -jar jenkins-cli.jar -s http://localhost:8085 -auth 'admin:Adm!n321' install-plugin
```

#### Install Bitbucket Branch Source using the Jenkins CLI

```
java -jar jenkins-cli.jar -s http://localhost:8085 -auth 'admin:Adm!n321' install-plugin cloudbees-bitbucket-branch-source

sudo service jenkins restart
```

#### upgrade-plugin

```
java -jar jenkins-cli.jar -s http://localhost:8085 -auth 'admin:Adm!n321' list-plugins | grep cloud
cloudbees-bitbucket-branch-source  Bitbucket Branch Source Plugin                  856.v04c46c86f911
cloud-stats                        Cloud Statistics Plugin                         0.20 (336.v788e4055508b_

java -jar jenkins-cli.jar -s http://localhost:8085 -auth 'admin:Adm!n321' install-plugin cloud-stats
sudo service jenkins restart
```

### disable-plugin

```
java -jar jenkins-cli.jar -s http://localhost:8085 -auth 'admin:Adm!n321' disable-plugin
```

#### Disable the github plugin using the Jenkins CLI.

Disable the `github` plugin using the Jenkins CLI.

```
java -jar jenkins-cli.jar -s http://localhost:8085 -auth 'admin:Adm!n321' list-plugins | grep github
github-api                         GitHub API Plugin                               1.318-461.v7a_c09c9fa_d63
github                             GitHub plugin                                   1.37.3.1
github-branch-source               GitHub Branch Source Plugin                     1771.v59b_6a_fa_1b_89e


java -jar jenkins-cli.jar -s http://localhost:8085 -auth 'admin:Adm!n321' disable-plugin github -restart -r
sudo service jenkins restart

```