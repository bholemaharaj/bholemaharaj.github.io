# *Various Docker Commands for in Windows 10, (on Mac they might be the same but different terminal)*

## Commands

* Get all containers **docker ps -a**
* Just the container thats running **docker ps**
* To remove the container **docker rm e89**, don't need to specify the entire id like **docker em e89fc43e2327** since the ids are unique
* Get images **docker images**
* Remove image **'docker rmi 7d58'** or **docker rmi 7d58d8582d10bef99dbbb0d270f830c40596c627c19e528136e218a3935c7c8a**
* To get/pull the docker image from Docker hub **docker pull kitematic/hello-world-nginx:latest**
* docker inspect [container name or id] e.g. docker inspect dynamodb-local
* Run this at powershell command line: **docker run -p 8080:5016 -v ${PWD}:/var/www -w "/var/www" node npm start**, see the curly braces around pwd
* Run this at bash command line: **docker run -p 8080:5016 -v $(pwd):/var/www -w "/var/www" node npm start**, see the parentheses around pwd
* Build command: docker build -t sbhole/node .
* Running the docker image: docker run -d -p 8080:3000 sbhole/node

