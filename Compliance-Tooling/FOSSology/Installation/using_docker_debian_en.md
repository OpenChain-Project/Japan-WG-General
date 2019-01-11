# Accessing the PostgreSQL database on the host OS from FOSSology inside the Docker container

FOSSology is a toolset that scans source code and detects OSS licenses and copyright information. It is a very useful tool for OSS license compliance. This article is intended to help beginners of FOSSology install and setup FOSSology on Docker container with an external PostgreSQL server running on the host OS (Debian 9).

## Content
1. Test Environment
2. Installation of Docker CE
3. Running FOSSology as a stand-alone image
4. Installation of PostgreSQL and creation of a DB
5. Running FOSSology accessing PostgreSQL on the host OS

## 1. Test Environment

The content written in this document was tested under the following environment.

|Item |Description |
|--- | --- |
|Host OS |Debian 9 (Stretch)|
|Network |Broadband access to the Internet|
|CPU |Intel(R) Core(TM) i3-3220T CPU @ 2.80GHz|
|RAM |4GB|

## 2. Installation of Docker CE

This section shows how to install Decker CE on Debian (host OS). Here is just a list of commands for installing Docker CE. Please refer to the following site for the detailed descriptions.
https://docs.docker.com/install/linux/docker-ce/debian/

```
$ sudo apt remove docker docker-engine docker.io
$ sudo apt update
$ sudo apt install apt-transport-https ca-certificates curl gnupg2 software-properties-common
$ curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
$ sudo apt-key fingerprint 0EBFCD88
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
$ sudo apt update
$ sudo apt install docker-ce
```
This command adds you to "docker" group so that you can run Docker without the root privilege. It seems that logout is required for this to take effect.

```
$ sudo gpasswd -a ${USER} docker
```
Run the hello-world image to see if Docker is installed correctly.

```
$ docker run hello-world
```
## 3. Running FOSSology as a stand-alone image

Following command runs a pre-built image of FOSSology from Dockerhub. It takes some time to download the docker image for the first time.

```
$ docker run -p 8081:80 fossology/fossology
```

Access http://IP_OF_DOCKER_HOST:8081/repo/ from your web browser with user fossy and password fossy.
cf. https://hub.docker.com/r/fossology/fossology/

At this point, FOSSology uses the internal database without data persistency. Check the container ID by "docker ps" command and then stop the container with "docker stop" command.

```
$ docker ps
CONTAINER ID        IMAGE                 COMMAND                  CREATED             STATUS              PORTS               NAMES
4a05838bafc4        fossology/fossology   "/fossology/docker-e…"   20 seconds ago      Up 18 seconds                           romantic_wu
$ docker stop 4a05838bafc4
```
## 4. Installation of PostgreSQL and creation of a DB

### 4.1 Installation of PostgreSQL

Install PostgreSQL on the host OS.

```
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install postgresql
```
### 4.2 Set a password for "postgres" user on the host OS

Set a password for "postgres" user. The password is arbitrary.

```
$ sudo passwd postgres
```

### 4.3 Create a database

Login as "postgres" and create a database "fossology". Then create a user "fossy" on the database with a password "fossy".

```

$ su - postgres
$ createdb fossology
$ createuser --pwprompt --interactive fossy
Enter password for new role: # Enter fossy here.
Enter it again: # Enter fossy here.
Shall the new role be a superuser? (y/n) n
Shall the new role be allowed to create databases? (y/n) n
Shall the new role be allowed to create more new roles? (y/n) n
```
## 5. Running FOSSology accessing PostgreSQL on the host OS

Start FOSSology with the following command. This time, "-p 8081:80" is not needed. (Discarded even if added)

```
$ docker run --network="host" -e FOSSOLOGY_DB_HOST="127.0.0.1" fossology/fossology
```
Access http://IP_OF_DOCKER_HOST/repo/ from your web browser.
