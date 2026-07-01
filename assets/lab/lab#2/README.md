# 20CYS402 - Distributed Systems and Cloud Computing
![](https://img.shields.io/badge/Batch-23CYS-gold) ![](https://img.shields.io/badge/UG-blue) ![](https://img.shields.io/badge/Subject-DSCC-blue) <br/>

## Lab#2 - Building Custom Docker Image 

### Aim
To create a custom Docker image by using a Dockerfile that installs packages, configures environment variables, sets a working directory, copies files, exposes a network port, and executes an application.

### Learning Outcomes 
After completing this exercise, students will be able to:

- Understand the purpose of a Dockerfile.
- Build a Docker image.
- Install software packages inside a Docker image.
- Configure environment variables.
- Set the working directory.
- Copy files from the host machine into the image.
- Expose application ports.
- Run applications using Docker containers.

### Practice Problem Statement (30 - 35 Minutes)
A software development team wants to package a simple Python web application inside a Docker container so that it can run consistently on any machine.

Create a Docker image that:
- Uses an official Python base image.
- Installs required packages.
- Sets environment variables.
- Sets the working directory.
- Copies application files.
- Exposes port 5000.
- Starts the application automatically.

#### Directory Structure

```
DockerLab1/

│── Dockerfile
│── app.py
│── requirements.txt
│── README.txt
```

#### Create the Flask Python App (app.py)

```
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Welcome to Docker Lab!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

#### Create Requirements (requirements.txt) 

```
Flask
```

#### Create a README file (README.md)

```
#20CYS402 - Distributed Systems and Cloud Computing
## Lab #2
```

#### Create Dockerfile

```
# Base Image
FROM python:3.12-slim

# Maintainer
LABEL maintainer="<<Your Name>>"
LABEL email="<<Your Email>>"

# Install packages
RUN apt-get update && \
    apt-get install -y curl nano && \
    apt-get clean

# Environment Variable
ENV APP_NAME="DSCC-Lab2-flaskappdockerimage"

# Working Directory
WORKDIR /app

# Copy files
COPY app.py .
COPY requirements.txt .
COPY README.txt .

# Install Python packages
RUN pip install --no-cache-dir -r requirements.txt

# Expose Port
EXPOSE 5000

# Run application
CMD ["python", "app.py"]
```

#### Build & Run the Image. Push the Image

Please follow the below instructions
- The image name shall be flaskappdockerimage
- Build the image 
- Run the image with port name mapped to 80XX (XX shall be your roll number)
- Push the image to your DockerHub

### Lab Problem Statement (55 - 60 Minutes)

A software company is developing a lightweight internal file-sharing service for its employees. The application is written in Python using Flask and must be packaged as a Docker image for deployment across multiple environments.

As a DevOps Engineer, your task is to containerize the application by creating a Docker image that satisfies the following requirements.

#### Requirements

Your Docker image shall:

1. Use an appropriate **official Linux or Python base image**.

2. Install all **software packages** required by the application.

3. Configure the following **environment variables**:
   - `APP_ENV=production`
   - `APP_PORT=8000`
   - `UPLOAD_DIR=/app/uploads`

4. Set the **working directory** to:
   ```
   /app
   ```

5. Copy the following files and directories from the host machine into the Docker image:
   - `server.py`
   - `requirements.txt`
   - `config.json`
   - `README.md`
   - `uploads/` directory

6. Install all **Python dependencies** listed in `requirements.txt`.

7. Expose the application on **port 8000**.

8. Configure the container so that the application **starts automatically** when the container is executed.

9. Build the Docker image using an appropriate **image name** and **tag**.

10. Run the Docker container and verify that the application is accessible from the host system through a web browser.


#### Directory Strucutre

```
filesharingdocker/

│── Dockerfile        (Students create this)
│── server.py
│── requirements.txt
│── config.json
│── README.md
│── uploads/
│     ├── sample1.txt
│     ├── sample2.txt
│     └── sample3.txt
```

#### Build & Run the Image. Push the Image

Please follow the below instructions
- The image name shall be filesharingdockerimage
- Build the image 
- Run the image with port name mapped to 80XX (XX shall be your roll number)
- Push the image to your DockerHub