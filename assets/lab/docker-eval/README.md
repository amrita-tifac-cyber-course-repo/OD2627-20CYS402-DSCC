# 20CYS402 - Distributed Systems and Cloud Computing
![](https://img.shields.io/badge/Batch-23CYS-gold) ![](https://img.shields.io/badge/UG-blue) ![](https://img.shields.io/badge/Subject-DSCC-blue) <br/>

## Docker Evaluation

### SET #1
Create a Docker Image for a Database Connector.

####  Objective
Build a Docker image for a database connector application. The application connects to a database using a specific programming language and requires the installation of certain packages. Set environment variables for database connection details and expose the application on a specific IP address and port.

#### Requirements
 - Choose a base image appropriate for the chosen programming language (e.g., Python, Node.js, Ruby).
 - Install the necessary packages for connecting to a database. Choose a simple database connector library compatible with your chosen language (e.g., psycopg2 for Python, mysql2 for Node.js, pg for Ruby).
 - Set environment variables for the following database connection details:
   - Database host
   - Database port
   - Database username
   - Database password
   - Database name
 - Expose the application on a specific IP address and port (e.g., IP: 0.0.0.0, Port: 8080).
 - Create a sample application code that uses the installed database connector library to connect to a database (you can use dummy values for the connection).

#### Tips
 - Use an official base image related to the chosen programming language.
 - Clearly document each step in the Dockerfile using comments.
 - Make sure to expose the correct port for your application.
 - Test the Docker image locally to ensure the database connector application is running.

#### Submission
Provide the following in your submission:
 - The Dockerfile used to build the Docker image.
 - The source code of the sample application demonstrating the database connection.
 - Link to Image in Docker Hub.

### SET #2

####  Objective
Create a Docker image for a Python-based web scraper (or language of your choice) that fetches titles of articles from a website (e.g., Hacker News, example.com). The application should install the necessary scraping packages, accept a target URL as an environment variable, and print the scraped data to the console.

#### Requirements
- Choose a base image appropriate for Python (e.g., python:3.10-slim).
- Install required packages: requests, beautifulsoup4.
- Set environment variable:
  - ```TARGET_URL```: the URL to scrape (e.g., https://news.ycombinator.com)
- The application should:
  - Read ```TARGET_URL``` from the environment
  - Fetch the HTML content
  - Parse and print the page’s main headings (```<h1>``` and ```<h2>```)
-  Expose port 8080, although it’s a CLI app, to simulate readiness for integration with a web front-end in the future.

#### Submission
Provide the following in your submission:
 - A word document with the detailed steps in building the image, running the image and pushing it to the hub with screenshots. 
 - The Dockerfile used to build the Docker image.
 - The source code of the sample application demonstrating the database connection.
 - Link to Image in Docker Hub.

#### Strucutre of scrapper.py

```
import os
import requests
from bs4 import BeautifulSoup

target_url = Read TARGET_URL from the environment

try:
    response = requests.get(target_url)
    do something

    print(f"\nScraping: {target_url}\n")
    for i, title in enumerate(titles, 1):
       do something

except Exception as e:
    print(f"Error fetching or parsing the URL: {e}")
```
