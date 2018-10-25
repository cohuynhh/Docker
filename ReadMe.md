# Docker

## CouchDB

**Command:** docker run -d --name couchdb couchdb

**Server:** localhost

**Port:** 5984

## ELK (Elasticsearch + Logstash + Kibana)

### Elasticsearch

**Image:** docker pull docker.elastic.co/elasticsearch/elasticsearch:6.3.2

**Command:** docker run -d -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" --name ElasticSearch docker.elastic.co/elasticsearch/elasticsearch:6.3.2

**Url:** <http://localhost:9200>

### Kibana

**Image:** docker pull docker.elastic.co/kibana/kibana:6.3.2

**Command:** docker run -d -p 5601:5601 --link ElasticSearch:elasticsearch --name Kibana docker.elastic.co/kibana/kibana:6.3.2

**Url:** <http://localhost:5601>

### Logstash

**Image:** docker pull docker.elastic.co/logstash/logstash:6.3.2

**Command:** docker run -d -p 9600:9600 -v C:\Logstash:/usr/share/logstash/pipeline/ --name Logstash docker.elastic.co/logstash/logstash:6.3.2

**Url:** <http://localhost:9600>

## MongoDB

**Command:** docker run -d --name mongo mongo

**Server:** localhost

**Port:** 27027

## Nginx

**Command:** docker run -d --name nginx -p 8080:80 nginx

**Url**: <http://localhost:8085>

## RabbitMQ

**Command:** docker run -d --name rabbitmq --hostname rabbitmq -p 5672:5672 rabbitmq

**Url**: <http://localhost:5672>

## Redis

**Command:** docker run -d --name redis redis

**Server:** localhost

**Port:** 6379

## SQL Server

**Command:** docker run -d -e "ACCEPT_EULA=Y" -e "MSSQL_PID=Developer" -e "SA_PASSWORD=S@1$&rv#r123456" -p 1433:1433 -v C:\SqlServer2017:/var/opt/mssql --name sqlServer2017 microsoft/mssql-server-linux:latest

**Server:** localhost,1433

**Login:** sa

**Password:** S@1$&rv#r123456

## Commands

### Prune

docker system prune --all --volumes --force

### Image

docker image --help (Help)

docker image build IMAGE_ID or IMAGE_NAME (Build)

docker image inspect IMAGE_ID or IMAGE_NAME (Inspect)

docker image ls (List)

docker image pull IMAGE_NAME:TAG (Pull)

docker image push IMAGE_NAME (Push)

docker image rm IMAGE_ID or IMAGE_NAME (Remove)

docker image tag IMAGE_ID or IMAGE_NAME TAG_NAME (Tag)

### Container

docker container --help (Help)

docker container exec -it CONTAINER_ID or CONTAINER_NAME ifconfig

docker container inspect CONTAINER_ID or CONTAINER_NAME (Inspect)

docker container logs CONTAINER_ID or CONTAINER_NAME (Logs)

docker container ls -a (List)

docker container restart CONTAINER_ID or CONTAINER_NAME (Restart)

docker container rm CONTAINER_ID or CONTAINER_NAME (Remove)

docker container run --name CONTAINER_NAME -p HOST_PORT:CONTAINER_PORT -v HOST_DIRECTORY:/usr/share/nginx/html nginx (Map ports and directories and run container)

docker container run --name CONTAINER_NAME IMAGE_NAME (Create and run container with a name)

docker container run --net NETWORK_NAME CONTAINER_ID or CONTAINER_NAME (Create and run container with network name)

docker container run IMAGE_NAME (Pull image and create and run container)

docker container start CONTAINER_ID or CONTAINER_NAME (Start)

docker container stop CONTAINER_ID or CONTAINER_NAME (Stop)

docker container tag CONTAINER_ID or CONTAINER_NAME TAG_NAME (Tag)

### Volume

docker volume --help (Help)

docker volume inspect VOLUME_NAME (Inspect)

docker volume ls (List)

docker volume rm VOLUME_NAME (Remove)

docker volume tag VOLUME_NAME TAG_NAME (Tag)

### Network

docker network --help (Help)

docker network connect bridge CONTAINER_ID or CONTAINER_NAME (Connect container to the Docker bridge)

docker network create --driver bridge NETWORK_NAME (Create)

docker network disconnect bridge CONTAINER_ID or CONTAINER_NAME (Disconnect container from the Docker bridge)

docker network inspect NETWORK_ID or NETWORK_NAME (Inspect)

docker network ls (List)

docker network rm NETWORK_ID or NETWORK_NAME (Remove)
