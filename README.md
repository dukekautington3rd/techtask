# techtask
The purpose of this code is to demostrate building a container stack that provides a front-end reverse proxy server and a backend web server.
credentials are required to access the content on the web server and are configureable in `docker-compose.yml` at build time.

The docker compose is instructed to build the containers at execution so it should take minimal steps to get up and running.

All you should need is
```
docker-compose up -d
```


if you prefer to build the containers ahead of time, `docker-compose build` will build the required containers before running.

This build automatically generates a self signed certificate and dynamically creates the credentials file based on the parameters in the docker-compose.yml file for accessing the secured content.

This container stack is built with the assumption that you have port 80 and 443 available on your host, so use it this way or modify the configuration to use a different set of ports.
