# 1_Managing-a-plugin

##### For More: [Managing Plugins (jenkins.io)](https://www.jenkins.io/doc/book/managing/plugins/)

### What are jenkins plugins?  


Jenkins plugins are the components of the Jenkins environment. Plugins are small, independent programs that can improve and extend the functionality of Jenkins CI/CD. There are over 1,900+ Jenkins plugins available right now and it keeps on increasing month by month. So there is a plugin to suit almost every need in software development. We can Install the Jenkins Plugins from the Jenkins Update Centre. Jenkins Update Centre is a centralised repository of Jenkins plugins which is being maintained by the Jenkins community.

### Install Plugins

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/OIbAopTvPIURJq6j-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/OIbAopTvPIURJq6j-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/aOthjTBjr0McQFWq-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/aOthjTBjr0McQFWq-image.png)

#### Install `github` plugin from Jenkins web UI.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/CXnGmnIhoaXQfzGj-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/CXnGmnIhoaXQfzGj-image.png)

##### Restart Jenkins if needed

```
service jenkins restart
```

##### Available Plugins

The Github plugin now appears under "Installed plugins"

##### [![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/rlE6oLDUodv1wBkC-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/rlE6oLDUodv1wBkC-image.png)

### Upgrade Plugins

1. Go to `Manage Jenkins`
2. Click on `Plugins`
3. Then search for `AWS Batch` plugin under `Updates` section and update it
4. Once installed click on `Restart Jenkins when installation is complete and no jobs are running`.
5. service jenkins restart

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/maJJVurETR5VjAwm-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/maJJVurETR5VjAwm-image.png)

### Uninstall Plugins

1. Go to `Manage Jenkins`
2. Click on `Plugins`
3. Then search for `AWS Batch` plugin under Installed section and click uninstall
4. Now Click Yes
5. service jenkins restart

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/yQtbW04076Ak5Xig-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/yQtbW04076Ak5Xig-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/GL9Ar9G74UoNu75U-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/GL9Ar9G74UoNu75U-image.png)

```
service jenkins restart
```

#### From CLI

```
#Other way is using Jenkins CLI, for that run below given command from the terminal:
java -jar jenkins-cli.jar -s http://localhost:8085 -auth 'admin:Adm!n321' restart
```

<div id="bkmrk--7"></div>