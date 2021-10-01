# Useful Docker commands:


docker ps - list all running containers
docker ps —all - list all containers

docker stop <container name> - stop running container
docker rm <container name> -remove container

docker images - list all images

docker exec -it <container name> /bin/sh -> connect to running container in interactive mode with bash terminal.


# mysql:
  

docker pull mysql

docker run -p 3307:3306 —name mysql-db -e MYSQL_ROOT_PASSWORD=xyz -d mysql:latest

Explanation:
docker run -p <outside_port>:<docker_con_port> —name <anyname> -e MYSQL_ROOT_PASSWORD=<passoword> -d <imagename>


# Phpmyadmin

docker run --name myadmin -d --link mysql:db -p 8004:80 phpmyadmin

Explanation:
docker run --name <anyname> -d --link <mysql db container name>:db -p <outside_port>:<server_port> <imagename>


# PGAdmin:

docker run -p 9003:80 -e PGADMIN_DEFAULT_EMAIL=email@gmail.com -e PGADMIN_DEFAULT_PASSWORD=xxx -d dpage/pgadmin4


Explaination:
docker run -p <outside_port>:<server_port> \
-e PGADMIN_DEFAULT_EMAIL=email@gmail.com \
-e PGADMIN_DEFAULT_PASSWORD=xxx \
-d <imagename>

docker port must be running port..
