# MERN stack example with Dockers
Mern stack code for tutorial and creating dockerimages
# Description
This project is based on MERN stack (MongoDB, Express, React, Node) with mulritier architecture. It contains a Node API, which is responsible to connect with DB and front end for the crud operation.

the 2nd part is to explain how we can create docker images of the complete project and interact with them.

# How to run source code in your development environment
1. First setup your MongoDB and Mongo express. Install both of them and check the connection.
Use below connection string if it is stand alone MomgoDB in your machine.

//Use this connection string if you are connecting standalone server
CONNECTIONURL = 'mongodb://admin:pass@localhost:27017'

If you are using docker container for MongoDB then use below connection string.

//Use this connection string if you are connecting from docker container server (host should be running container name like: "mern-stack-example-mongodb-1")
//CONNECTIONURL = 'mongodb://admin:pass@mern-stack-example-mongodb-1:27017'
How to use MongoDB as a docker container, please check below section.

2. First copy code from git url: https://github.com/matif-saleem/mern-app.git and copy in your local system project folder named "MERNProjects" for example.

3. Open terminal and change directoy to your project folder
/path/MERNProjects/

4. Now change directory to server and run below command
/path/MERNProjects/server
node --env-file=config.env server

5. Now open another terminal and change directory to client and run below command
/path/MERNProjects/client
npm run dev

Now Your server and client are up and running.

6. Go to browser and run http://localhost:5173/ You will see below page. 

Perform some operations to test the functionalities and check everything is working fine.

# How to create docker images and containerize them
If you want to directly run your production ready mern app, create idocker images of server and client and execute thier containers.

1. Mongodb and MongoExpress containers

   Open terminal and execute below docker-compose command.
   docker-conpose -f /path/MERNProjects/mongo.yaml up

You can see docker execute the command and container should be up and run. Not dowm the container name which will be used as hostname in MongoDB connection string in our server. Update your connection string in config.enf file in server folder.

2. Go to the server folder by using /path/MERNProjects/server and create server image using docker file and run below command:
   docker build -t mern-server:1.0 .
   
3. Go to the server folder by using /path/MERNProjects/client and create server image using docker file and run below command:
   docker build -t mern-client:1.0 .

4. Now execute below docker-compose command.
   docker-conpose -f /path/MERNProjects/mernapp.yaml up
   
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
