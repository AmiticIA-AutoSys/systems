### docker-build-n-registry

This stack is used to build images and store them on a local registry.
Equivalent to DockerHub it stores docker images.
With this registry Portainer open-source can pull images from it.
The images can be build on any machine and pushed to this registry.

#### Example 

For build and pushing image to local registry `vtiger65:1.0` (version 1.0)

##### Register the remote builder 

```
docker buildx create --name vtiger-builder \
  --driver remote \
  tcp://server.pfklabs.online:1234   
```

Then set to use it 

```bash
docker buildx use vtiger-builder
```

##### Build on the remote builder and push to the remote register

```bash
docker buildx build \
  --builder vtiger-builder \
  --tag server.pfklabs.online:5000/vtiger65:1.0 \
  --push .
```

##### Using on docker-compose 

Then on docker-compose.yaml we can use the image.
And Portainer will fetch it from the server directly. 

```docker-compose.yaml
services:
  vtiger65:
    image: manager-node:5000/vtiger65:1.0
...
```





