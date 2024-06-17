# 3_CMD-VS-ENTRYPOINT

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/NMDhb4JQ68cvNur4-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/NMDhb4JQ68cvNur4-image.png)

CMD and ENTRYPOINT are two Dockerfile instructions that together define the command that runs when your container starts. You must use these instructions in your Dockerfiles so that users can easily interact with your images. Because CMD and ENTRYPOINT work in tandem, they can often be confusing to understand. This article helps eliminate any potential disparity in this realm.

In a [cloud-native](https://www.bmc.com/blogs/cloud-native-devops/) setup, Docker [containers](https://www.bmc.com/blogs/what-is-a-container-containerization-explained/) are essential elements that ensure an application runs effectively across different computing environments. These containers are meant to carry specific tasks and processes of an application workflow and are supported by Docker images.

The images, on the other hand, are run by executing Docker instructions through a Dockerfile. There are three types of instructions (commands) that you use to build and run Dockerfiles:

- **RUN.** Mainly used to build images and install applications and packages, RUN builds a new layer over an existing image by committing the results.
- **CMD.** Sets default parameters that can be overridden from the Docker Command Line Interface (CLI) when a container is running.
- **ENTRYPOINT.** Default parameters that cannot be overridden when Docker Containers run with CLI parameters.

Any Docker image must have an ENTRYPOINT or CMD declaration for a container to start. Though the ENTRYPOINT and CMD instructions may seem similar at first glance, there are fundamental differences in how they build container images.