## Kubernetes

#### Service Mesh

A service mesh is a software layer that handles all communication between services in applications. This layer is composed of containerized microservices. As applications scale and the number of microservices increases, it becomes challenging to monitor the performance of the services. To manage connections between services, a service mesh provides new features like monitoring, logging, tracing, and traffic control. It’s independent of each service’s code, which allows it to work across network boundaries and with multiple service management systems.

#### Serverless

Serverless means that the developers can do their work without having to worry about infrastructure at all. Behind serverless computing there are networksm storage and traditional computing components that needs to be defined in the cloud

#### Scalability

Option to increate or decrease capacity when needed. Autoscaling increases the resilience and availability of cloud native applications.

- Horizontal Scaling: Additional instances to meet with increasing demand
- Vertical Scaling: Increasing hardware resources in compute instances

#### Containers

A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another. To run a container, container runtime is needed. This is the layer between the host operating system and the container itself

#### Docker

```txt
- Download the image(If not existing download)
docker run ubuntu

- Check currently running containers
docker ps

- Show all containers
docker ps -a

docker run -d nginx

- Show ubuntu configurations in json
docker inspect ubuntu

- Stop container
docker stop $container_name/$container_id

- Delete container
docker rm $container_name/$container_id

docker run --name webserver -d -p 8080:80 nginx
                                  host:container_port

- Check all the docker images
docker image ls

- Tagging an image
docker tag $img_name $img_name:version

- Check Image history
docker image history $container_id

- Bulding docker image
docker build -t $image_name .
```
