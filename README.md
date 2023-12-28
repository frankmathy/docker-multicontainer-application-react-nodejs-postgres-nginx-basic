# Multicontainer application

Codeching - video 8 - Dockerizing a React application with Node.js Postgres and NginX - dev and prod - step by step - PART 1

See https://youtu.be/-pTel5FojAQ?si=IicYFIDKs0lQyOyv

It contains React client, Node.js backend, PostgreSQL and Nginx

You can run it in development mode: docker-compose up --build
It contains Dockerfiles for client, server which you should push to your docker hub to be able
to pull them down when in next tutorial we will use them in Kubernetes.

Note: When during startup of the client a strange SSL error appears, call the following from the command line to enable the legacy SSL provider:
export NODE_OPTIONS=--openssl-legacy-provider
See https://stackoverflow.com/questions/69692842/error-message-error0308010cdigital-envelope-routinesunsupported

Build React Docker Dev Image

```
docker build .  -f Dockerfile.dev -t stylerhun/multi-client
```
