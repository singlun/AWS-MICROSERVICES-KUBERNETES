# Udagram - Photo Sharing App develop as Continuous Deployment with Jenkins

## Table of Contents

* [OverView](#OverView)
* [Setup Environment](#Setting-Environment)
* [Installation Docker](#Installation-Docker)
* [Project Reference Sources Or Links](#references)

## OverView

In this project, we will apply the skills we have acquired in this cloud engineering course to design, deploy and operate a cloud native photo sharing application. We will reuse our existing application and convert and extend into a microservice architecture. The microservice architecture makes it more easier to scale it to large systems. They are great enablers for continuous integration and delivery too. This includes independent scaling, independent releases and deployments  and independent development so that ACH service has its own codebase. After the application is divided into smaller services, we will containerize it and deploy it with Jenkins. This includes deployment pipeline, scalability, observability, Services, Networking and deployment strategies to service the system. 

For this project we will uses Oracle Vitualbox Virtual Machine for simulating the development Environment. For simplicity we will setup 2 development virtual machine, one is for Docker, and the other is for Kubernetes. 

## Setting-Environment

 * Docker
    1. To install please follow the this link: https://docs.docker.com/toolbox/toolbox_install_windows/. After Installed you will be able to use most of the docker functions. `TAKE NOTE: PLEASE DO NOT UPGRADE THE VIRTAULBOX`. Upgrading the virtualbox will causes un-expected issues, which causes the Udagram app to not fuction properly.


 * Setting the Envormnet Variables:
    For Windows, Open the `File Explorer` and right click the `The PC`, Select the properties. From pop-up window choose `Advance System Settings`, then choose `Environment Variables`.

    Please add the following Environment Variables (fill in your values, for JWT_SECRET fill in 'jwt').
    - AWS_MEDIA_BUCKET
    - AWS_PROFILE
    - AWS_PROFILE
    - JWT_SECRET
    - POSTGRESS_DB
    - POSTGRESS_HOST
    - POSTGRESS_PASSWORD
    - POSTGRESS_USERNAME
    - URL
    
## Installation-Docker

* The only options to install Udagram is by cloning from the git hub please follow the instructions below .

    1. From the Ubuntu/Linux Terminal, type in the command:
        * git clone `https://github.com/programmingwebsite/aws-microservices-kubernetes.git`. 
    2. After cloning, browse to the exercises folder. From the exercise folder,  you need to install the packages and dependencies for     `udacity-c3-frontend`, `udacity-c3-restapi-feed` and `udacity-c3-user`. Type in the following command for each folder.
        * npm ci
    3. Build and Create the docker Images.
        * Browser to the folder `udacity-c3-deployment/docker`. Type the following command: 
        `docker-compose -f docker-compose-build.yaml build --parallel`. This will build all the images for the Udagram Project.
    4. Push all the images to the Docker Hub Repository. You need to have a Docker Hub account.
        * From the Docker Terminal. Type in `docker login`, you will be prompt in the username and password.
        * To push all the images to Docker Hub , type in `docker-compose -f docker-compose-build.yaml push`.

      
## References

* Code References
    * [Udacity](https://www.udacity.com/)
    * [GitHub](https://github.com/)
    * [Generating ssh key and add it to the agent](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
    * [Linux Too Many Open Files Solution](https://blog.csdn.net/fdipzone/article/details/34588803)
    * [kubectl (exec error: unable to upgrade connection: Forbidden ) Solution](https://github.com/opsnull/follow-me-install-kubernetes-cluster/issues/255)
    * [Kubernetes Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
    * [Installing Kubeadmin , Kubelet and Kubectl](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/)
    * [Running HA Kubernetes Cluster Using Kubeone in AWS](https://medium.com/@alexander_15213/running-ha-kubernetes-clusters-on-aws-using-kubeone-535b93af57ab)
    * [How to install Kubernetes on AWS Cluster using Kubeone](https://github.com/kubermatic/kubeone/blob/master/docs/quickstart-aws.md)
    * [Learn Kubernetes Basic](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
    * [Install and setup Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)