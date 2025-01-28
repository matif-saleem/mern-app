# MERN stack example with Dockers
Mern stack code for tutorial and creating dockerimages

# Description
This project is based on MERN stack (MongoDB, Express, React, Node) with mulritier architecture. It contains a Node API, which is responsible to connect with DB and front end for the crud operation.
The 2nd part is to explain how we can create docker images of the complete project and interact with them.

# How to run source code in your development environment
1. First setup your MongoDB and Mongo express. Install both of them and check the connection.
2. Use below connection string if it is stand alone MomgoDB in your machine.
  
_//Use this connection string if you are connecting standalone server
CONNECTIONURL = 'mongodb://admin:pass@localhost:27017'_

3. If you are using docker container for MongoDB then use below connection string.

_//Use this connection string if you are connecting from docker container server (host should be running container name like: "mern-stack-example-mongodb-1")
//CONNECTIONURL = 'mongodb://admin:pass@mern-stack-example-mongodb-1:27017'_

_How to use MongoDB as a docker container, please check below section._

4. First copy code from git url: https://github.com/matif-saleem/mern-app.git and copy in your local system project folder named "MERNProjects" for example.

5. Open terminal and change directoy to your project folder:

_/path/MERNProjects/_

6. Now change directory to server and run below command:

_/path/MERNProjects/server_
_node --env-file=config.env server_

7. Now open another terminal and change directory to client and run below command:

_/path/MERNProjects/client_
_npm run dev_

Now Your server and client are up and running.

8. Go to browser and run http://localhost:5173/ You will see below page. 

# How to create docker images and containerize them

If you want to directly run your production ready mern app, create idocker images of server and client and execute thier containers.

## Mongodb and MongoExpress containers

Open terminal and execute below docker-compose command:

_docker-conpose -f /path/MERNProjects/mongo.yaml up_

You can see docker execute the command and container should be up and run. Not dowm the container name which will be used as hostname in MongoDB connection string in our server. Update your connection string in config.enf file in server folder.

Go to the server folder and create server image using docker file and run below command:

_/path/MERNProjects/server
docker build -t mern-server:1.0 ._

Go to the server folder and create server image using docker file and run below command:

_/path/MERNProjects/client
docker build -t mern-client:1.0 ._

Now execute below docker-compose command.

_docker-conpose -f /path/MERNProjects/mernapp.yaml up_

You can see all four containers are up and running. Go to browser and run http://localhost:5173/

# Usage

It can be used for learning purposes as well as for basic MERN app template for your future projects.

# Technologies used

1. MongoDB
2. Mongo Express
3. ExpressJS
4. ReactJS
5. NodeJS
6. ViteJS
7. Dockers

# Disclaimer
Use at your own risk; not a supported MongoDB product.
