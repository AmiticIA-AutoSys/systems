### Vps Deploy

```bash
sudo apt-get update ; apt-get install -y apparmor-utils
hostnamectl set-hostname manager1
```
At /etc/hosts replace `localhost` to `manager1`

Download and install docker

```bash
curl -fsSL https://get.docker.com | bash
```
Set up docker swarm and public network

```bash
docker swarm init
docker network create --driver=overlay --attachable network_public
```

Deploy traefik stack.
Copy from traefik/docker-stack-deploy.yaml (using nautilus) to vps server 

```bash
docker stack deploy --prune --resolve-image always -c docker-stack-deploy.yaml traefik
```

Deploy portainer stack [official docs](https://docs.portainer.io/start/install-ce/server/swarm/linux)
Copy from portainer/docker-stack-deploy.yaml (using nautilus) to vps server 

```bash
docker stack deploy --prune --resolve-image always -c docker-stack-deploy.yaml portainer
```