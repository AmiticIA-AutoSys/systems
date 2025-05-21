### docker-build-n-registry

This stack is used to build images and store them on a local registry.
Equivalent to DockerHub it stores docker images.
With this registry Portainer open-source can pull images from it.
The images can be build on any machine and pushed to this registry.

#### Example 

For build and pushing image to local registry `vtiger65:1.0` (version 1.0)

```bash
docker buildx build \
   --builder tcp://server.pfklabs.online:1234 \
   --tag server.pfklabs.online:5000/vtiger65:1.0 \
   --push .
```

Then on docker-compose.yaml we can use the image.
And Portainer will fetch it from the server directly. 

```docker-compose.yaml
services:
  vtiger65:
    image: manager-node:5000/vtiger65:1.0
...
```

(If you never used buildx before: `docker buildx create --use` once an Docker will remember.)

