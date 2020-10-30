# CI CD Pipeline using Jenkins to deploy a Docker container

In this project a ci cd pipeline structure is set up using Jenkins to build a docker container. We have 4 servers:

**1: Dev server**

**2: cicd server**

**3: build server**

**4: production server**

The docker project is created in the **Dev server** and pushed to github. When a new commit is made to the github it triggers **Jenkins** to invoke a playbook. The playbook is written to clone the github repository, build a docker image and to create a docker container.

**Jenkins** is installed and configured on the **CI CD server**. A new freestyle project is created and github is selected as the source code management option. The webhook url from jenkins project is added to our github project repository and link to the github repo is provided to **Jenkins**. Path to our playbook and inventory file is also given in the build section.


When a new commit is made to our github repository, **Jenkins** invokes the playbook and clones the repository in the **Build server**. A new docker image is built in the **Build server** and is pushed to docker hub.

In the **Production server**, the new docker image is downloaded from docker hub and a docker container is launched using the docker image.




