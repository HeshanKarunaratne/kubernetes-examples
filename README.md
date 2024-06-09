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

- Delete image
docker image rm $image_name
```

- Example: Pulling and Pushing to our registry and then Downloading from our regisry

```txt
docker pull fedora
docker tag fedora:latest localhost:5000/myfedora
docker push localhost:5000/myfedora
docker rmi fedora
docker pull localhost:5000/myfedora

- Building and tagging to an existing repo
docker build -t docker.io/heshankarunaratne/gitopsmap .

- Pushing to that repo
docker push docker.io/heshankarunaratne/gitopsmap

- Delete container using name
docker rm $container_name
docker rm adoring_kilby

- Delete image using IMAGE ID
docker rmi $image_id

- Downloading image from our repo
docker pull docker.io/heshankarunaratne/gitopsmap
```

#### Copy On Write

```txt
- Create sh file
vim hello.sh

- Add below script
#!/bin/bash
echo hello

- Give permission
chmod +x heelo.sh

- Create base Dockerfile
vim Dockerfile.base

- Add below script
FROM ubuntu:20.04
COPY . /app

- Create Dockerfile
vim Dockerfile

- Add below script
FROM koe/base-image:1.0
CMD /app/hello.sh

- Build the base image
docker build -t koe/base-image:1.0 -f Dockerfile.base .

- Build the final image
docker build -t koe/final-image:1.0 -f Dockerfile .

- Review both images with history
docker history $image_name
```

#### Volumes

```txt
- Create a volume
docker volume create myvol

- Get list of volumes
docker volume ls

- Inspect volume
docker volume inspect $volume_name

docker run -it --name voltest --rm -v myvol:/data nginx:latest /bin/sh
```

#### Git

```txt
- Check all the global configs
git config -l --global

- Set user information
git config --global user.name "$username"
git config --global user.email "$email"

- Set the branch
git branch -M main

- Set the remote origin
git remote add origin $url

- Push to origin
git push -u origin main

- Create branch
git branch $branch_name

- Switch to branch
git switch $branch_name

- Check all the branches
git branch --list

- Set upstream
git push --set-upstream origin $branch_name

- Check difference
git diff $branch_name main

- Switch to main branch
git switch main

- Merge $branch_name to current(main) branch
git merge $branch_name
```

#### Minikube

```cmd
- Download and install minikube, Make sure you have hyperv
minikube start --driver=hyperv 

- Minimal Cluster resources
kubectl get all

- Minimal Cluster resources in All namespaces
kubectl get all -A

```
