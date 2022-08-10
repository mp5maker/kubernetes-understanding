

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


```bash
systemctl enable --now docker
systemctl status docker
grep docker /etc/group
usermod -aG docker student
newgrp docker
cd /etc/containers/registries.d
```