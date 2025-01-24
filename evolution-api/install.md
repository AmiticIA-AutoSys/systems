I followed the official [tutorial](https://doc.evolution-api.com/v2/pt/requirements/database) for database setup.
Then the [tutorial of redis](https://doc.evolution-api.com/v2/pt/requirements/redis) and finally the [docker tutorial](https://doc.evolution-api.com/v2/pt/install/docker) without installing those prerequisites evolution-api can't work.

The docker-compose.yaml is the final summary of all effort and it's fully working on docker on ubuntu server 24.03.

In the directory run the command bellow. That will download, install and run PostgreSQL, Redis and Evolution's docker images.  
Also setting all the proper configurations of network and environment variables.

```bash
sudo docker compose up -d
```

Then to make to stop and remove all of them run

```bash
sudo docker compose down
```

If your domain changes needs to change the env. variable `SERVER_URL` 
You need `AUTHENTICATION_API_KEY` set here to log-in on evolution-server. 

More on the docs on [Environment Variables](https://doc.evolution-api.com/v2/pt/env)


For while using clodflare argo-tunnel to my cheap domain evoapi.talvez.site