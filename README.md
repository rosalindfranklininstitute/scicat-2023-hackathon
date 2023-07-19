# Scicat Workshop 2023 - hackathon 
In this hackathon the team will work on improving the search function in Scicat. This repo contains a unified development environment for the hackathon. 

We have a docker compose file which spins up the basic services for Scicat: mongodb, frontend, and backend. 

## Running the test environment
To run this environment create an environment file with the following settings:

```
EXPRESS_SESSION_SECRET: burrowing_owl
JWT_SECRET: goblin_shark
```

Run services:
`docker-compose up`

Run services in live development mode on the backend undo the commented lines. Make sure the paths are correct and update if needed in your environment.
```
  # volumes:
    #  - ../scicat-backend-next:/app
    #  - ./scicat-backend-next/node_modules:/app/node_modules
```
To see the data login with the `ingestor` account: 
username: `ingestor`
password: `aman`


## Adding the data 
To add the data provided for the hackathon please use the following:

```
docker-compose exec -T mongo sh -c "mongorestore --archive --nsTo=\"scicat.*\"  --nsFrom=\"dacat.*\"" < /data/scicat-hackathon.dump
```

