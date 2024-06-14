# 3_Controller-Isolation

Username: admin

Password: Adm!n321

### Install Role-based Authorization plugin

Let's extend some Authorization capabilities of Jenkins to support even more authorization schemes.  
Install Role-based Authorization plugin.

Note:

Observe the new available options under Authorization using the standard <span style="color: rgb(0, 0, 0); background-color: rgb(251, 238, 184);">Manage Jenkins &gt; Security screen after the plugin installation.</span>

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/66TB1uj1JiNdIkfH-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/66TB1uj1JiNdIkfH-image.png)

### Select the option that best describes the concept of distributed builds in Jenkins.

#### <span style="background-color: rgb(251, 238, 184); color: rgb(0, 0, 0);">Builds that should be excecute on other nodes and not the built-in node.</span>

### Built-in node

By default, Jenkins run its builds on the `built-in node`. It is done to make smooth transition towards learning Jenkins but is `inadvisable` in long term.  
It is due to the fact that any builds running on the built-in node have the same level of access to the controller file system as the Jenkins process.

#### Configure Jenkins to prevent builds from running on the Built-In Node directly?

Navigate to Manage Jenkins » Manage Nodes and Clouds screen and change the number of Executors to 0 for the Built-In Node.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/GizvrGSAxivUQbT4-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/GizvrGSAxivUQbT4-image.png)