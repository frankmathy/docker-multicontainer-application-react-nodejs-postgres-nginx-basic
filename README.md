# Multicontainer application

Codeching - video 8 - Dockerizing a React application with Node.js Postgres and NginX - dev and prod - step by step - PART 1

See https://youtu.be/-pTel5FojAQ?si=IicYFIDKs0lQyOyv and https://youtu.be/OVVGwc90guo?si=z41-zbarZL_73nuO

It contains React client, Node.js backend, PostgreSQL and Nginx

You can run it in development mode: docker-compose up --build
It contains Dockerfiles for client, server which you should push to your docker hub to be able
to pull them down when in next tutorial we will use them in Kubernetes.

Note: When during startup of the client a strange SSL error appears, call the following from the command line to enable the legacy SSL provider:
export NODE_OPTIONS=--openssl-legacy-provider
See https://stackoverflow.com/questions/69692842/error-message-error0308010cdigital-envelope-routinesunsupported

Build and Run React Docker Dev Image

```
docker build -f Dockerfile.dev -t frankmathy/multi-client .
docker run -it -p 4002:3000 frankmathy/multi-client
```

Build and Run Node Server Dev Image

```
docker build -f Dockerfile.dev -t frankmathy/multi-server .
docker run -it -p 4003:5000 frankmathy/multi-server
```

Build and Run React Prod App, Push To Dockerhub

```
docker build -t frankmathy/multi-client .
docker run -it -p 3000:3000 frankmathy/multi-client
docker push frankmathy/multi-client
```

Build and Run Server Prod API, Push to Dockerhub

```
docker build -t frankmathy/multi-server .
docker run -it -p 4002:5000 frankmathy/multi-server
docker push frankmathy/multi-server
```
