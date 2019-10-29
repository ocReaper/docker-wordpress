docker-wordpress
================
[![](https://badge.imagelayers.io/centurylink/wordpress.svg)](https://imagelayers.io/?images=centurylink/wordpress:latest 'Get your own badge on imagelayers.io')
Out-of-the-box Wordpress docker image without MySQL 

## What is WordPress?
WordPress is one of the most versatile open source content management systems on the market. WordPress is built for high performance and is scalable to many servers, has easy integration via REST, JSON, SOAP and other formats, and features a whopping 15,000 plugins to extend and customize the application for just about any type of website.

https://www.wordpress.org/

## Configuration

The image can be altered via the following environment variables to fit your need:

* `DB_NAME` refers to the database name in your mysql server
* `DB_PASSWORD` refers to the password for the above mentioned database
* `DB_1_PORT_3306_TCP_ADDR` refers to the database host address
* `DB_1_PORT_3306_TCP_PORT` refers to the database host port

> It's important to note that this image relies on the `root` database user!

## How to use this image

### Use the one liner in your PHP project

```bash
$ docker run -it --rm --name my-running-wp-app centurylink/wordpress --env DB_NAME=name --env DB_PASSWORD=password --env DB_1_PORT_3306_TCP_ADDR=localhost --env DB_1_PORT_3306_TCP_PORT=3306
```

### Create a `docker-compose.yml` file in your PHP project

For larger projects it's easier to create a compose file and mount your files.

```yml
version: "3.7"

services:

  wordpress:
    image: centurylink/wordpress
    environment:
      DB_NAME: name
      DB_PASSWORD: password
      DB_1_PORT_3306_TCP_ADDR: localhost
      DB_1_PORT_3306_TCP_PORT: 3306
    ports:
      - 80:80
```
