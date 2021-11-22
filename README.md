# Docker Setup for NodeJS
A boilerplate for dockerized implementation of NodeJS application.

## Specifications / Infrastructure Information
- MySQL
- Postfix
- Data Volume
- Node/NPM
- Redis

## Prerequisites
- git
- docker
- docker-compose

## Getting Started
Copy `.env` for docker in root directory
```
cp .env.example .env
```
Fill in variables
```
ENVIRONMENT=development                 # development/staging/production
PROJECT_NAME=YOUR_PROJECT_NAME_HERE     # Prefix for the docker containers to be created
MYSQL_ROOT_PASSWORD=p@ss1234!           # root password of the root mysql user
MYSQL_DATABASE=YOUR_DATABASE_NAME       # database that will be created
MYSQL_USER=YOUR_DATABASE_USER           # mysql user
MYSQL_PASSWORD=YOUR_DATABASE_USER       # user password
```

## Build all the containers
```
docker-compose build
```
Start the containers
```
docker-compose up -d
```
Run the following command to login to any docker container
```
docker exec -it CONTAINER_NAME bash
```

## Adding NodeJS script.
Create your first NodeJS script by adding new js file inside `src` directory.
  
`src/my-script.js`
```
console.log('Hello world.');
```

## Running NodeJS script.
```
docker-compose run node my-script.js
```

For deployment, use command:
```
docker-compose run node npm run build
```
