Docker running Nginx, PHP-FPM, MySQL PHPMyAdmin and WordPress.

## Overview

1. [Install prerequisites](#install-prerequisites)

    Before installing project make sure the following prerequisites have been met.

2. [Clone the project](#clone-the-project)

    We’ll download the code from its repository on GitHub.


3. [Run the application](#run-the-application)

    By this point we’ll have all the project pieces in place.

4. [Use Makefile](#use-makefile) [`Optional`]

    When developing, you can use `Makefile` for doing recurrent operations.

5. [Use Docker Commands](#use-docker-commands)

    When running, you can use docker commands for doing recurrent operations.

## Clone the project

To install [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git), download it and install following the instructions :

```sh
git clone git@github.com:alexionnn/test_project.git
```

Go to the project directory :

```sh
cd test_project

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
