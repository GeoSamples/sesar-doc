---
name: install_install_SESAR_app_as_a_container
title: Install SESAR App as a container
date: 01/12/2020
---

# Install SESAR App as a container
### Set up as Docker container environment

#### Set up development environment
  * git clone SESAR repository to 'sesar' directory
  * cd sesar
  * create docker image
    ```
    docker build . -t sesar:v8
    ```
  * Start a container
    * command line
     ```
     docker run -d -it --rm -p 80:80 -v $PWD:/var/www/html -v $PWD/../uploads:/var/www/uploads -v $PWD/../container_logs:/var/log/apache2 --name sesar_v8 sesar:v8
     ```
     * use docker-compose [docker-compose.yml](https://github.com/iedadata/sesar/blob/development/docker-compose.yml)
     ```
       docker-compose up &
     ```
  * You can access the running container as below.
     ```
     docker exec -it sesar_v8 bash
     ```
#### Set Up Test enviroment on Docker Engine.
  * Login to docker hub
    ```
    docker login as earthchemrepo
    ```
  * Download the image
    ```
    docker pull earthchemrepo/sesar:v8
    ```
  * Launch the application as a container
    * From command line
    ```
    docker run -d -it --rm -p 80:80 -v $PWD:/var/www/html -v $PWD/../uploads:/var/www/uploads -v $PWD/../container_logs:/var/log/apache2 --name sesar_v8 earthchemrepo/sesar:v8
    ```
     * use docker-compose [docker-compose.yml](https://github.com/iedadata/sesar/blob/development/docker-compose.yml)
     ```
       docker-compose up &
     ```
  * You can access the running container as below.
     ```
     docker exec -it sesar_v8 bash
     ```
