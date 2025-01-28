# MERN Stack Example with Docker Containers

## Project Overview
This project demonstrates a multi-tier MERN stack application (MongoDB, Express, React, Node.js) with Docker containerization. It includes a Node.js API for database interaction and a React frontend for CRUD operations. The project also guides you through creating Docker images for both the server and client, enabling easy deployment.

## Technologies Used
* MongoDB (Database)
* Mongo Express (Database Management Tool)
* Express.js (Node.js Web Framework)
* React.js (JavaScript UI Library)
* Node.js (JavaScript Runtime Environment)
* Vite.js (Frontend Build Tool)
* Docker (Containerization Platform)

## Running the Project Locally

**Prerequisites:**

* MongoDB and Mongo Express installed and running
* Git client installed
* Create a project folder named "**MERNProjects**"


**Steps:**

**1. Clone the Project:**
```
git clone https://github.com/matif-saleem/mern-app.git
```

**2. Change Directory:**

```
cd MERNProjects
```

**3. Configure MongoDB Connection:**

* Go to config.env file in the server directory.
* Add the appropriate connection string based on your MongoDB setup (standalone or Docker container).

**Standalone MongoDB:**

```
CONNECTIONURL = 'mongodb://admin:pass@localhost:27017'
```

**Dockerized MongoDB:**

```
CONNECTIONURL = 'mongodb://admin:pass@mern-stack-example-mongodb-1:27017'
```

Replace admin and pass with your actual credentials.

**4. Start the Server:**

```
cd server
node --env-file=config.env server
```

**5. Start the Client:**

```
cd client
npm run dev
```

**6. Access the Application:**

Open http://localhost:5173/ in your browser.

## Creating Docker Images and Containers

1. Run MongoDB and Mongo Express with Docker Compose:

```
cd mern

docker-conpose -f mongo.yaml up
```

This command creates and starts Docker containers for MongoDB and Mongo Express. Note down the container name for MongoDB (e.g., mern-stack-example-mongodb-1), as it will be used in the server's connection string.

2. Build Docker Images:

*Server:

```
cd server

docker build -t mern-server:1.0 .
```

*Client:

```
cd client

docker build -t mern-client:1.0 .
```

3. Run the Application with Docker Compose:

```
cd mern

docker-conpose -f mernapp.yaml up
```

This command starts Docker containers for the server, client, MongoDB, and Mongo Express.

## Usage

This project serves as a learning tool and a basic MERN application template for future projects.

## Disclaimer

Use this project at your own risk. It is not an officially supported MongoDB product.
