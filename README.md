# Docker + CodeIgniter 3 + Phpmyadmin

This image serves as a starting point for CodeIgniter projects.

## Quick Start

Get an CodeIgniter application running the fastes way.

```shell
$ git pull https://github.com/fklement/docker-codeigniter
$ cd docker-codeigniter
$ docker-compose up
```

## Run your existing application

If you want to run your exisisting project you need to pull and configure it before you start the docker container.

### 1. Pull the current repo

```shell
$ git pull https://github.com/fklement/docker-codeigniter
$ cd docker-codeigniter
$ mkdir myapp
$ cd myapp
$ git pull <url-of-your-project>
```

### 2. Create the database with phpmyadmin

You can simply use phpmyadmin to import your existing database.
Visit `http://localhost` to get to phpmyadmin.

> Username: root  
> Password: root  

### 3. Configure your application

Now you need to configure your application to use the databases that is running inside docker.

To do so you need to manipulate the credentials of your application normally located under `/myapp/application/config/database.php`.


> 'hostname' => 'mariadb',  
'username' => 'root',  
'password' => 'root',  
'database' => 'name-of-your-database',


### 4. Fire up docker

In the root folder of this application you now can start up docker.

```shell
$ docker-compose up
```

### 5. Access the application

The application now should be available via `http://localhost:8000`