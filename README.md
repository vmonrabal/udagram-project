# Refactor Udagram App intoto Microservices and Deploy Project
This is the solution to the exercise proposed in Chapter 4 - Monolith to Microservices at Scale

Starter project was [here](https://github.com/vmonrabal/nd9990-c3-microservices-exercises/tree/master/project)

## Getting started
This repository contains all the requirements asked in the *Project Rubric*
- `Deployment` folder contains all the projects `deployment.yml` and `service.yml` files
- `screenshots` folder contains the images required in the *Project Rubric*
- `udagram-<projectname>` folder contains the `Dockerfile` and `.travis` files. Also the folder `udagram-reverser-proxy` contains the `nginx.yml` file
- `aws-secret.yml` and `udagram-secrets.yml` are the templates used to deploy the secrets in `K8s`
- `README.md` is this file

## Exercise instructions
Below are the solutions provided to each point of the *Project Rubric*

### Containers and Microservices
> Divide an application into microservices

[Udagram Feed API](https://github.com/vmonrabal/udagram-feed)
[Udagram User API](https://github.com/vmonrabal/udagram-user)

The other project repositories are:
[Udagram Frontend](https://github.com/vmonrabal/udagram-frontend)
[Udagram Reverse Proxy](https://github.com/vmonrabal/udagram-reverse-proxy)

> Build and run a container image using Docker

Dockerfiles and DockerHub screenshot of each project can be found in:


| Application | Docker File| DockerHub |
| :---------- | :--------- | :-------- |
| Udagram Feed API | [Dockerfile](https://github.com/vmonrabal/udagram-project/blob/master/udagram-feed/Dockerfile) | [DockerHub Image](https://github.com/vmonrabal/udagram-project/blob/master/screenshots/docker-feed.png) |
| Udagram User API | [Dockerfile](https://github.com/vmonrabal/udagram-project/blob/master/udagram-user/Dockerfile) | [DockerHub Image](https://github.com/vmonrabal/udagram-project/blob/master/screenshots/docker-feed.png) |
| Udagram Frontend API | [Dockerfile](https://github.com/vmonrabal/udagram-project/blob/master/udagram-frontend/Dockerfile) | [DockerHub Image](https://github.com/vmonrabal/udagram-project/blob/master/screenshots/docker-feed.png) |
| Udagram Reverse Proxy API | [Dockerfile](https://github.com/vmonrabal/udagram-project/blob/master/udagram-reverse-proxy/Dockerfile) | [DockerHub Image](https://github.com/vmonrabal/udagram-project/blob/master/screenshots/docker-feed.png) |

### Independent Releases and Deployments
> Use Travis to build a CI/CD pipeline

| Application | Travis File|
| :---------- | :--------- |
| Udagram Feed | [.travis](https://github.com/vmonrabal/udagram-project/blob/master/udagram-feed/.travis.yml)|
| Udagram User | [.travis](https://github.com/vmonrabal/udagram-project/blob/master/udagram-user/.travis.yml)|
| Udagram Frontend | [.travis](https://github.com/vmonrabal/udagram-project/blob/master/udagram-frontend/.travis.yml)|
| Udagram Reverse Proxy | [.travis](https://github.com/vmonrabal/udagram-project/blob/master/udagram-reverse-proxy/.travis.yml)|

**Travis Builds**
![Travis Builds](https://raw.githubusercontent.com/vmonrabal/udagram-project/master/screenshots/travis-builds.png)

### Service Orchestration with Kubernetes
> Deploy microservices using a Kubernetes cluster on AWS

**kubectl get pods**
![Get Pods](https://raw.githubusercontent.com/vmonrabal/udagram-project/master/screenshots/kubectl-get-pods.png)

**kubectl describe services**
![Describe Services](https://raw.githubusercontent.com/vmonrabal/udagram-project/master/screenshots/kubectl-describe-services.png)

> Use a reverse proxy to direct requests to the appropriate backend

**kubectl describe service**
![Describe Reverse Proxy](https://raw.githubusercontent.com/vmonrabal/udagram-project/master/screenshots/kubectl-describe-reverse.png)

**Postman Frontend**
![Frontend Reverse Proxy](https://raw.githubusercontent.com/vmonrabal/udagram-project/master/screenshots/reverse-proxy-frontend.png)

**Postman Feed**
![Feed Reverse Proxy](https://raw.githubusercontent.com/vmonrabal/udagram-project/master/screenshots/reverse-proxy-feed.png)

**Postman User**
![User Reverse Proxy](https://raw.githubusercontent.com/vmonrabal/udagram-project/master/screenshots/reverse-proxy-user.png)

> Configure scaling and self-healing for each 

![Describe HPA](https://raw.githubusercontent.com/vmonrabal/udagram-project/master/screenshots/kubectl-describe-hpa.png)

### Debugging, Monitoring and Logging
> Use logs to capture metrics for debugging a microservices deployment

![Describe Reverse Proxy](https://raw.githubusercontent.com/vmonrabal/udagram-project/master/screenshots/kubectl-api-logs.png)
