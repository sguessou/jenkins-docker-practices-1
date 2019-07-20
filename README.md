# Devops Practices 
## Database backups automation using Docker, Jenkins, MySQL and AWS S3.
### Dokerizing Jenkins
The first step in this howto is to create a docker container running Jenkins.   
Go here for all the steps needed for that --> [Dockerizing Jenkins](JENKINS.md)

### Docker Cheat Sheet

#### Cleaning up any resources (images, containers, volumes and networks) that are dangling but not associated with a container:
```
$ docker system prune 
```            
For removal of stopped containers and all unused images add the **-a** flag:

#### Removing Docker Images
List images:
```
$ docker images -a
```                
Remove images
```
$ docker rmi IMAGE IMAGE ...
```        
Remove all images
```
$ docker rmi $(docker images -a -q)
```
#### Removing Containers
Remove container
```
$ docker rm ID_OR_NAME ID_OR_NAME
```
Run and remove a container
```
$ docker run --rm IMAGE_NAME
```
Remove all exited containers
```
$ docker rm $(docker ps -a -f status=exited -q)
```
Stop and remove all containers
```
$ docker stop $(docker ps -a -q)
$ docker rm $(docker ps -a -q)    
```
#### Removing Volumes
List volumes
```
$ docker volume ls
```        
Remove volumes
```
$ docker volume rm VOLUME_NAME VOLUME_NAME
```    