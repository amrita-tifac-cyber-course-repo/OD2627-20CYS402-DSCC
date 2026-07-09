# 20CYS402 - Distributed Systems and Cloud Computing
![](https://img.shields.io/badge/Batch-23CYS-gold) ![](https://img.shields.io/badge/UG-blue) ![](https://img.shields.io/badge/Subject-DSCC-blue) <br/>

## Lab#3 - Docker Compose: Running Multiple Docker Container
![](https://img.shields.io/badge/Date-09_July-blue)

### Aim
To create and manage a multi-container application using Docker Compose while demonstrating persistent data storage through Docker named volumes.

### Learning Outcomes

After completing this exercise, students will be able to:
- Understand the purpose of Docker Compose.
- Create and run services using a docker-compose.yml file.
- Define and use Docker named volumes.
- Store and retrieve persistent data using volumes.
- Verify that data persists even after containers are removed and recreated.
- Inspect Docker volumes and understand their lifecycle.

### Practce Problem Statement (50 Minutes)
A web development team wants to deploy a simple static website using Docker Compose. The website content should be editable directly from the host machine without rebuilding the container, and the application should use a Docker named volume to demonstrate persistent storage.

Using Docker Compose, create a project that:
 - Uses the official Nginx image as the web server.
 - Serves a custom HTML page from the host machine using a bind mount.
 - Maps the web server to port 8080 on the host.
 - Creates a named volume for the Nginx container.
 - Starts the web server using Docker Compose.
 - Verifies that the website is accessible through a web browser.
 - Modifies the ```index.html``` file on the host and confirms that the changes are reflected in the browser without rebuilding or restarting the container.
 - Inspects the created named volume using Docker commands.
 - Demonstrates the difference between docker compose down and docker compose down -v by observing the persistence and removal of the named volume.
   
#### Directory Structure

```
docker-compose-lab/
│
├── docker-compose.yml
├── website/
    └── index.html
```

#### Create index.html

```
<!DOCTYPE html>
<html>
<head>
    <title>Docker Compose Lab</title>
</head>
<body>
    <h1>Welcome to Docker Compose</h1>
    <h2>Your Name</h2>
    <p>This page is served using Docker Compose and Volumes.</p>
</body>
</html>
```

### Create docker-compose.yml

```
services:

  web:
    image: nginx:latest

    ports:
      - "8080:80"

    volumes:
      - ./website:/usr/share/nginx/html
      - nginx_logs:/var/log/nginx

volumes:
  nginx_logs:
```

#### Build & Run the Image. Push the Image


### Evaluation (40 Minutes)

#### Evaluator 
| **Roll Number ** | **Faculty Evaluator** |
|:---------------------:|-------------|
| 03 – 23  | Dr. Jevitha K P |
| 26 – 43 | Dr. Praveen K |
| 44 – 63 | Mr. Ramaguru Radhakrishnan |

#### Rubrics
| **Evaluation Criteria** | **Marks** |
|--------------------------|:---------:|

