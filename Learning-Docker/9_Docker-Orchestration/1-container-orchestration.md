# 1_Container-Orchestration

### Container Orchestration

Container orchestration is just a solution that consist of a set of tools and scripts that can help host containers in a production environment. Typically, a container orchestration solution consists of multiple Docker hosts that can host container. That way even if one fails, the application is till accessible through others.

A container orchestration solution easily allows you to deploy hundreds or thousands of instances of you application with a single command.

This is a command used for Docker Swarm. We will look at the command itself in a bit.

```
docker service create --replicas=100 nodejs

```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/0Sr4D8sVPJIve6dG-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/0Sr4D8sVPJIve6dG-image.png)

#### Docker Swarm

With Docker Swarm, you could now combine multiple Docker machines together into a single cluster. Docker Swarm will take care of distributing your services or your application instances into separate hosts for high availability and for load balancing across different systems and hardware.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/z46ArVIasUI3541k-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/z46ArVIasUI3541k-image.png)

#### Setup Docker Swarm

To set up a Docker swarm, you must first have hosts or multiple hosts with Docker installed on them. Then you must designate one host to be the manager or the master or the swarm manager as it is called and others as slaves or workers. Once you're done with that, run the docker `swarm init `command on the swarm manager, and that will initialize  
the swarm manager.

The output will also provide the command to be run on the workers to copy the command and run it on  
the worker nodes to join the manager. After joining the swarm, the workers are also referred to as nodes, and you're now ready to create services and deploy them on the swarm cluster. So, let's get into some more details.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/eJmhaSYZUdupBYSh-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/eJmhaSYZUdupBYSh-image.png)

#### Docker Service

So, let's get into some more details. As you already know, to run an instance of my web server, I run the docker run command and specify the name of the image I wish to run.

This creates a new container instance of my application and serves my web server. Now that we have learned how to create a swarm cluster, how do I utilize my cluster to run multiple instances of my web server? Now, one way to do this would be to run the docker run command on each worker node.

  
But that's not ideal, as I might have to log in to each node and run this command, and there could be hundreds  
of nodes. I will have to set up load balancing myself, I'll have to monitor the state of each instance myself, and if instances were to fail, I'll have to restart them myself. So, it's going to be an impossible task. That is where Docker swarm orchestration comes in. Docker

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/2wVqDr2sb9MfZC4N-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/2wVqDr2sb9MfZC4N-image.png)

The key component of swarm orchestration is the Docker service. Docker services are one or more instances of a single application or service that runs across the nodes in the swarm cluster, for example, in this case, I could create a Docker service to run multiple instances of my web server application across worker nodes in my swarm cluster.

  
For this, I run the docker service create command on the manager node and specify my image name there, which is my web server in this case and use the option replicas to specify the number of instances of my web server I would like to run across the cluster.

Since I specified three replicas and I get three instances of my web server distributed across the different  
worker nodes, remember the Docker service command must be run on the manager node and not on the worker node.

The docker service create command is similar to the docker run command in terms of the options passed such as the -e environment variable, the -p for publishing ports, the network option to attach container to a network.

<div class="notranslate" id="bkmrk--4" style="all: initial;"></div>