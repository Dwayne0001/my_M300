FROM mysql/mysql/mysql-server

EXPOSE 3306


RUN echo 'issa fertig<3'
network
docker run --name mysql  mysql:latest

docker run --name=mysql --network Net1 -p 3306:3306 -d mysql/mysql-server:latest