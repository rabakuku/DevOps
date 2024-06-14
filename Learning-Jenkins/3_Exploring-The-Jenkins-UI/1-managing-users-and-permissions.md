# 1_Managing-users-and-permissions

##### For more: [Managing Jenkins](https://www.jenkins.io/doc/book/managing/)

### Create a Jenkins user 

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/6q0JbkDJnDE60Eqs-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/6q0JbkDJnDE60Eqs-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/xTIdpeiq0l8C0NWD-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/xTIdpeiq0l8C0NWD-image.png)

#### Create a Jenkins user as per the details provided below.

  
**A.** Username: `tony`  
**B.** Password: `T0ny123`  
**C.** Full Name: `Tony Hawk`

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/lftNUVlu6YgKQdRw-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/lftNUVlu6YgKQdRw-image.png)

#### Role-based Authorization Strategy

Install the `Role-based Authorization Strategy` plugin and enable the `Role-Based Strategy` authorization in Jenkins security settings.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/uJLUeYOZPvUdCu6B-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/uJLUeYOZPvUdCu6B-image.png)

```
service jenkins restart
```

#### authorization in Jenkins security settings

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/qVmXiuC1uwTF9Ztc-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/qVmXiuC1uwTF9Ztc-image.png)

### Create a role name

Create a role named `developers` and make sure it has overall `Read` permissions alone. Also assign role called `developers` to the user called `tony`.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/A5diMokSM1GKe5jL-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/A5diMokSM1GKe5jL-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/aeKRFgn8dK926W3q-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/aeKRFgn8dK926W3q-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/Ptki53DIOlJy3BvC-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/Ptki53DIOlJy3BvC-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/g9E4EdWWjme1PWMM-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/g9E4EdWWjme1PWMM-image.png)

####  Install the Matrix Authorization Strategy plugin 

#####  Using the Project-based Matrix Authorization Strategy assign some permissions that would allow tony to build the mytest job.

1. Go to `Manage Jenkins`, then click on `Plugins` tab.
2. Click on `Available` section and search for `Matrix Authorization Strategy` plugin.
3. Then mark the box `check` and click on `Install without restart` button.
4. After that click on `Restart Jenkins when installation is complete and no jobs are running`.

##### Steps to enable Project-based Matrix Authorization Strategy:

1. Go to `Manage Jenkins`, then click on `Security` tab.
2. Select `Project-based Matrix Authorization Strategy` under `Authorization` section.
3. Click on `Add User` and enter user name `tony`. After that it will appear in the `matrix`.
4. Enable `Read` under `Overall` column, `Build` and `Read` under `Job` column for user `tony`.
5. Now click on `Save` button on your bottom of the page.
6. Login as `tony` user into the Jenkins server and build the job named `mytest`.