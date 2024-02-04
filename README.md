## Docker Container - Ubuntu 20.04 - Apache, MySQL, PHP, PYTHON, and phpMyAdmin

## Introduction

There are two main 'versions' of the docker image. The table below shows the different tags you can use, along with the PHP, MySQL and Apache versions that come with it.

Component | `latest-2004-php7` `latest-2004-php8`
---|---
[Apache][apache] | `2.4.41`
[MySQL][mysql] | `8.0.26`
[PHP][php] | `7.4.23`/`8.0.10`
[phpMyAdmin][phpmyadmin] | `5.1.1`

## Developing the image
### Building and running
```bash
# Clone the project from Github
git clone https://github.com/0001ca/docker-uapp.git
cd docker-uapp

# Build the images
docker build --build-arg PHP_VERSION=8.0 -t=0001ca/uapp:latest -f Dockerfile .
docker build --build-arg PHP_VERSION=8.0 -t=0001ca/uapp:latest-2004-php8 -f Dockerfile .
docker build --build-arg PHP_VERSION=7.4 -t=0001ca/uapp:latest-2004-php7 -f Dockerfile .

#Run the image as a container adding app data folder and persistant mysql
docker run -i -t -p "80:80" -v ${PWD}/app:/app -p 3306:3306 -v ${PWD}/mysql:/var/lib/mysql 0001ca/uapp:latest

```



