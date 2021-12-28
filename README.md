Docker running Nginx, PHP-FPM, MySQL PHPMyAdmin and WordPress.

## Overview

1. [Install prerequisites](#install-prerequisites)

    Before installing project make sure the following prerequisites have been met.

2. [Clone the project](#clone-the-project)

    We’ll download the code from its repository on GitHub.


3. [Run the application](#run-the-application)

    By this point we’ll have all the project pieces in place.

    
___

## Install prerequisites

To run the docker commands without using **sudo** you must add the **docker** group to **your-user**:

```
sudo usermod -aG docker your-user
```

For now, this project has been mainly created for Unix `(Linux/MacOS)`. Perhaps it could work on Windows.

All requisites should be available for your distribution. The most important are :

* [Git](https://git-scm.com/downloads)
* [Docker](https://docs.docker.com/engine/installation/)
* [Docker Compose](https://docs.docker.com/compose/install/)

Check if `docker-compose` is already installed by entering the following command : 

```sh
which docker-compose
```
## Clone the project

To install [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git), download it and install following the instructions :

```sh
git clone git@github.com:alexionnn/test_project.git
```

Go to the project directory :

```sh
cd test_project
```

Setup password in environment variables in files:
```sh
env/mysql.env
env/wordpress.env
```
___

## Run the application


1. Start the application :


    ```sh
    docker-compose up -d
    ```

    **Please wait this might take a several minutes...**

    ```sh
    docker-compose logs -f # Follow log output
    ```

3. Open your favorite browser :

    * [http://localhost] WordPress
    * [http://localhost/pma] PHPMyAdmi
   
4. Stop and clear services

    ```sh
    docker-compose down -v
    ```
    

## Project environment 

env/mysql.env
```sh
MYSQL_DATABASE - This variable is optional and allows you to specify the name of a database to be created on image startup. If a user/password was supplied (see below) then that user will be granted superuser access (corresponding to GRANT ALL) to this database.
```

```sh
MYSQL_ROOT_PASSWORD - This variable is mandatory and specifies the password that will be set for the MySQL root superuser account.
```
```sh
MYSQL_USER, MYSQL_PASSWORD - These variables are optional, used in conjunction to create a new user and to set that user's password. This user will be granted superuser permissions (see above) for the database specified by the MYSQL_DATABASE variable. Both variables are required for a user to be created.
```

env/wordpress.env

```sh
WORDPRESS_DB_HOST - name of a database host to be used by WordPress
```
```sh
WORDPRESS_DB_USER - name of a database user to be used by WordPress
```
```sh
WORDPRESS_DB_PASSWORD - name of a database password to be used by WordPress
```
```sh
WORDPRESS_DB_NAME - name of a database to be used by WordPress
```
