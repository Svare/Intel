# Commands

docker run nginx
    # Start a Container
docker ps # List Containers, each container gets a randon name when created

docker ps -a

docker stop ID/Name

docker rm ID/Name

docker images # List Images

docker rmi nginx

docker pull nginx # Get the Image but don't run it

docker run ID/Name command # Run a command

docker exec ID/Name cat /etc/hosts

docker -d hub_name # Run container detached
docker attach ID/Name

docker stop/start ID/Name

docker --name custom_name hub_name

# Run Commands

docker run redis:tag
docker run -i
docker run -it
docker run -p 80:5000 hub_name
docker run -v /docker/host/dir:/doker/dir hub_name # Volume Mapping
docker inspect ID/Name
docker logs ID/Name

# Enviroment Variables

docker run -e APP_COLOR=green

# Network

docker network ls

# Databases
## Tunneling
    ssh -L 4444:localhost:3306 root@192.168.228.129

docker ps --no-trunc
## MySQL
docker run -it --rm mysql:tag --verbose --help
docker run -p 3306:3306 --name poc-mysql-2 -e MYSQL_ROOT_PASSWORD=Hola123., -d mysql:latest --log-raw=FALSE --local-infile=FALSE --sql-mode=STRICT_ALL_TABLES
## MariaDB
docker run -it --rm mariadb:tag --verbose --help
docker run -p 3306:3306 --name poc-mariadb -e MYSQL_ROOT_PASSWORD=Hola123., -d mariadb:latest --local-infile=FALSE --sql-mode=STRICT_ALL_TABLES