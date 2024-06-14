# 1_Backup-And-Restore-Jenkins

##### For More: [Backing-up/Restoring Jenkins](https://www.jenkins.io/doc/book/system-administration/backing-up/)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/VhA6uDwO61ApCETi-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/VhA6uDwO61ApCETi-image.png)

### Under which location Jenkins store its data primarily?

#### - $JENKINS\_HOME

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/Loi08dzGqUKz2phH-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/Loi08dzGqUKz2phH-image.png)

### Which of the following is the main configuration file of Jenkins?

#### - config.xml

### Install the ThinBackup Jenkins plugin.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/fUGyKBytsLyj7Lf5-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/fUGyKBytsLyj7Lf5-image.png)

#### Backup Jenkins using ThinBackup

Backup Jenkins (including plugins) under `/var/lib/jenkins/jenkins_backup` directory using `thinBackup` plugin.

##### Create Directory and Change Permission

```
mkdir /var/lib/jenkins/jenkins_backup
chmod 777 /var/lib/jenkins/jenkins_backup
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/p8LZKtb2T1Nqg7W3-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/p8LZKtb2T1Nqg7W3-image.png)

##### Create Backup Settings

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/E749kIMlvBkJPf8z-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/E749kIMlvBkJPf8z-image.png)

##### Backup Now

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/xkAm02og8IBkLPSd-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/xkAm02og8IBkLPSd-image.png)

##### check directory

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/Fd3M2ibvsSwGK950-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/Fd3M2ibvsSwGK950-image.png)

#### Restore Jenkins using ThinBackup

##### Go to ThinkBackup

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/6MUOX8ehPRaj50vv-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/6MUOX8ehPRaj50vv-image.png)

##### Select Backup

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/1sFejzXUmZfLoJfl-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/1sFejzXUmZfLoJfl-image.png)

##### Restart Jenkins

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/2f7eFKeyKciBUaQt-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/2f7eFKeyKciBUaQt-image.png)

```sh
service jenkins restart
```