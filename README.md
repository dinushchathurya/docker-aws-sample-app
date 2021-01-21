# Deploy simple To-Do App which created using Node.js, Express, MongoDb & ejs to AWS 


## Installation

1. Clone repo
2. run `npm install` 

## Create Mongo Image

1. run `docker pull mongo`

## Create Mongo-express Image

1. run `docker pull mongo-express`

## Create Docker Network

1. run `docker network create mongo-network`

## Start mongodb

```
docker run -d -p 27017:27017 
-e MONGO_INITDB_ROOT_USERNAME=admin 
-e MONGO_INITDB_ROOT_PASSWORD=password 
--name mongodb 
--net mongo-network mongo`
```

## Start mongo-express

```
docker run -d -p 8081:8081 
-e ME_CONFIG_MONGODB_ADMINUSERNAME=admin 
-e ME_CONFIG_MONGODB_ADMINPASSWORD=password  
-e ME_CONFIG_MONGODB_SERVER=mongodb 
--name mongo-express
--net mongo-network 
mongo-express
```

## Create Database

1. Navigate to `http://localhost:8081/`
2. Create Database & Collections

## Usage 

1. run `npm run dev`
2. Navigate to `localhost:3000`
