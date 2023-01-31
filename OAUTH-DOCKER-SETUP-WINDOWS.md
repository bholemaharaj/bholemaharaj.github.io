# *OAuth Setup on Windows 10 Machine*

___

While setting up the OAuth Service described under the heading <strong><u>Getting started: running unit tests</u></strong>, performing step number 1.b.i on [Developer Onboarding to the Oauth Service Page][1], the tables were not getting created in the instance of dynamodb running in the docker on WIndows 10.

## Setup

Instead of running step 1.b.i do following described on [AWS documentation page][2]

Copy the following code to a file on your disk, and save it as docker-compose.yml and then navigate to the directory on command line

```yml
version: '3.8'
services:
  dynamodb-local:
    command: "-jar DynamoDBLocal.jar -sharedDb -dbPath ./data"
    image: "amazon/dynamodb-local:latest"
    container_name: dynamodb-local
    ports:
      - "8000:8000"
    volumes:
      - "./docker/dynamodb:/home/dynamodblocal/data"
    working_dir: /home/dynamodblocal
```

 and then execute following,

```bash
    docker-compose up
```

[1]:https://confluence.ellucian.com/pages/viewpage.action?spaceKey=PS&title=Developer+Onboarding+to+the+Oauth+Service
[2]:https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.DownloadingAndRunning.html
