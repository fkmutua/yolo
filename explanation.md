Explanation of how the project works:

Clone the repo: https://github.com/fkmutua/yolo

Get inside  yolo directory 

Run docker compose docker-compose up --build

Run docker ps -a to get the container names, image tags and the IDs


I used node Node. js 14 which is the latest and small in size 

For Dockerfiles:

FROM node:14 -  the base image to build from

WORKDIR /backend and client  - A working directory to hold and run  application code

COPY this copies the package.json and package-lock.json files containing project dependencies to the working directory inside the docker image

RUN npm install - Install project dependencies

COPY - to  Copy project source code to the working directory inside the docker image

RUN npm run build for building purposes of the project 

EXPOSE 3000 - Expose port 3000 and 5000 for client and backend respectively 

Use CMD [ "serve", "-s", "build", "-l", "3000" ] - Start the server

Docker-compose.yml file hosts 3 containers as below:

yolo_backend_1 container that runs on port 5000

yolo_client_1 container that runs on port 3000

yolo_mongo_1  container that contains mongo db which runs on port 27017 

Networks - All containers are in yolo_app bridge network