# My-Private-Hub


commands:


docker run -d -p 8081:8081 -p 5001:5000 --name nexus -v nexus-data:/nexus-data sonatype/nexus3

docker exec nexus cat /nexus-data/admin.password

docker stop nexus
docker rm nexus 
sudo rm -rf /path/to/nexus-data/db
sudo rm -rf /path/to/nexus-data/etc
sudo rm -rf /path/to/nexus-data/keystores
sudo rm -rf /path/to/nexus-data/admin.password

docker volume rm nexus-data


docker run -d \
  -p 8081:8081 \
  -p 8082:8082 \
  --name nexus \
  -v nexus-data:/nexus-data \
  sonatype/nexus3

docker logs -f nexus    

docker tag python_health_check:v0.1 localhost:8082/python_health_check:v0.1

docker login localhost:8082
docker push localhost:8082/python_health_check:v0.1


docker rmi python_health_check:v0.1
docker rmi localhost:8082/python_health_check:v0.1
docker pull localhost:8082/python_health_check:v0.1


docker run -d -p 5001:5000 --name validated_app localhost:8082/python_health_check:v0.1
