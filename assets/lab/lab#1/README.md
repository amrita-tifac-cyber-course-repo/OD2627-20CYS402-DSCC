# 20CYS402 - Distributed Systems and Cloud Computing
![](https://img.shields.io/badge/Batch-23CYS-gold) ![](https://img.shields.io/badge/UG-blue) ![](https://img.shields.io/badge/Subject-DSCC-blue) <br/>

## Docker 

Docker is 
- a software platform where
  - build,
  - test,
  - deploy applications quickly.
- packages software into standardized units called containers
- these containers have everything the software needs to run
  - libraries,
  - system tools,
  - code,
  - runtime
 
<p align="center">
  <img src="https://d1.awsstatic.com/onedam/marketing-channels/website/aws/en_US/product-categories/containers/approved/images/2e5f22ba-2678-4df9-af45-7e575f5d5590.801e619624462059ed2678866fd430490d521208.png" width=600 />
</p>

### Docker Examples
- [Simple Dockerfile Building](https://www.youtube.com/watch?v=0HCBQpfQE7o)
- [Demo Dockerfile Building](https://www.youtube.com/watch?v=lrTBwlW46Ik)
- [Demo Image Running](https://www.youtube.com/watch?v=ND-qkZVc3KM)
- [Pushing Image to DockerHub](https://www.youtube.com/watch?v=pBdN1OlWGQc)

## Lab#1 - Building First Docker Image and Pushing to Docker Hub
![](https://img.shields.io/badge/Date-25_June-blue)

### Aim
To create the first Docker image by using a Dockerfile, understand how Dockerfile works, how to build a image, how to tag images, how to create a repository in dockerhub, how to push the image to dockerhub and how to run.

## Learning Outcome
By the end of this exercise, you will be able to:

- Understand the purpose and structure of a Dockerfile.
- Learn how a Dockerfile works to build Docker images.
- Create a Docker image using the docker build command.
- Apply tags to Docker images using the docker tag command.
- Create a repository on Docker Hub.
- Push a Docker image to a Docker Hub repository using the docker push command.
- Pull and run the Docker image using the docker run command.
- Verify that the container is running successfully.

### Creating Dockerfile and Building Docker image

#### Creating Dockerfile
- Create a file named ```Dockerfile``` (without extension)

```
FROM busybox
```

#### Build Docker Image
- This will build your image without any name (tag)
```
docker build . > Dockerfile
```

- To build docker image with the tag
```
docker build . > Dockerfile -t demoimage
```

#### Check for the Build Images
- The below commands should display all the tagged docker images only
```
docker images
```

- To display the untagged docker images (dangling images)
```
docker image ls --filter "dangling=true"
```

### Pushing to Docker Hub

1. Login to Dockerhub
2. Create a docker repository named ```firstdockerimage``` 
3. In your terminal:
   - Login into your docker with the command:
     ```
     docker login
     ```
   - Retag your image from ```demoimage``` to ```<<dockerusername>>/firstdockerimage``` with the command:
     ```
     docker tag demoimage <<dockerusername>>/firstdockerimage
     ```
   - push the newly tagged image to the DockerHub with the command:
     ```
     docker image push <<dockerusername>>/firstdockerimage
     ```
