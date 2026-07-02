# 20CYS402 - Distributed Systems and Cloud Computing
![](https://img.shields.io/badge/Batch-23CYS-gold) ![](https://img.shields.io/badge/UG-blue) ![](https://img.shields.io/badge/Subject-DSCC-blue) <br/>

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
   - Login into your docker with the command: ```docker login```
   - Retag your image from ```demoimage``` to ```<<dockerusername>>/firstdockerimage``` with the command: ```docker tag demoimage <<dockerusername>>/firstdockerimage```
   - push the newly tagged image to the DockerHub with the command: ```docker image push <<dockerusername>>/firstdockerimage```
