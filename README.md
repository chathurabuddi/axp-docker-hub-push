# AXP Push to Docker Hub Script
### AXP Internal Gateway Pre Configured Docker Image
![build status](https://github.com/chathurabuddi/axp-docker-hub-push/workflows/igw-push-to-docker-hub/badge.svg)
![igw](https://img.shields.io/docker/v/chathurabuddika/igw.svg)

The following command starts a Linux Ubuntu-based Internal Gateway Docker image.

```
$ docker run --name igw -d -p 3306:3306 -p 8243:8243 -p 8280:8280 -p 9443:9443 -p 9444:9444 chathurabuddika/igw
```
Here, only ports 3306, 8243, 8280, 9443 and 9444 have been mapped to the corresponding Docker host (host machine on top of which containers are spawned) ports. You may map other container service ports to Docker host ports as desired.

The Docker exec command allows you to run commands inside a Docker container. The following command line will give you a bash shell inside the container you created:

```
$ docker exec -it igw bash
```
To start DEP and KM nodes use the following commands inside the container:

```
cd /IGW/wso2telcohub-4.1.0-SNAPSHOT/bin/
./axpserver.sh

cd /IGW/wso2is-km-5.6.0/bin/
./wso2server.sh start
```
