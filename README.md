# A simple MERN stack application

This app has three primary components:
The Frontend(React, Tailwind CSS, HTML); A web application for user to interact.
The Backend(Nodejs, Express); Handling the logic of the frontend
The Database(MongoDB); Stores data and communicates with the backend to retrieve and store data from the user.

### Create a network for the docker containers

`docker network create mern`

### Build the client

```sh
cd mern/frontend
docker build -t mern-frontend .
```

### Run the client

`docker run --name=frontend --network=mern -d -p 5173:5173 mern-frontend`

### Verify the client is running

Open your browser and type `http://localhost:5173`

### Run the mongodb container

`docker run --network=mern --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongo:latest`

### Build the server

```sh
cd mern/backend
docker build -t mern-backend .
```

### Run the server

`docker run --name=backend --network=mern -d -p 5050:5050 mern-backend`

## Using Docker Compose

`docker compose up -d`
