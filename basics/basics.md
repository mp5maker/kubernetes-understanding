

* Containers needs to be running something by default
* Virtual machines do not need anything to run by default

* Containers has container engines
* Virtual machines has hypervisor

* Containers do not contain kernel
* Virtual machines contains kernel

### Containers
* Containers are running on linux
* Namespaces provide strict isolation at a linux kernel level
* CGroups provides resource allocation to guarantee dedicated resources to be available
* SeLinux can be used to enforce security in a containerized environment
* Early container solution built on top of the above components
* LXC is one such early container solutions
* Docker in 2013 made containers big.
* One of the main features that it added the docker registry, where container images can be exchanged

### Docker Architecture
* Docker uses a client-server architecture
* Docker daemon is responsible for building, runnin and downloading container images
* The docker client is responsible for communicating with the docker server


### Podman
* An alternative to Docker for the red hat enterprise (created to avoid monopoly)


### Standardization in containers
* OCI is the Open Container Initiative
* It standarizes use of container images and runtime specification
* This ensures compatibility between container that were created in different container engine environment


### Setup
```bash
systemctl enable --now docker
systemctl status docker
grep docker /etc/group
usermod -aG docker student
newgrp docker
cd /etc/containers/registries.d
```

### Dockerfile
* It is a way to automate container build
* It contains all instructions required to build a container image
* Instead of distributing images, we can distribute the Dockerfile
* Use docker build . to build the container image based on the Dockerfile
* Images will be stored in the local system, but can be direct to a repository


### Common Docker commands
```bash
docker ps -a
docker start [container_id]
docker inspect [container_id] | less
docker inspect --format='{{.NetworkSettings.IPAddress}}' [container_name]
docke exec -it [container_id] bash/sh
docke run -it [container_id] bash/sh
Ctrl-p, Ctrl-q
docker stop [container_id]s
docker rm [container_id]
docker images
docker prune -f image|volume|system
docker rmi --force [image_name]
```


### Docker Network
* Different drivers are available to define how networking should happen
* bridge: the default network deriver, used when applications run in standalone containers that need to communicate
* host: only in Docker swarm; used for standalone containers, where the container connects to the host network directly
* overlay: used in Docker swarm to connect multiple Docker daemons together
* macvlan: mac address can be assigned to a container to have it appear as a physical device on the network
* none: disables networking, which is useful if a custom network driver is used