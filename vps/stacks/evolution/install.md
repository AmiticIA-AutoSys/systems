### Postgresql

I followed the official [tutorial](https://doc.evolution-api.com/v2/pt/requirements/database) for database setup.

Must create evolution database on postgresql from bash on container of pgadmin, dbeaver-ce

```bash
sudo -u postgres createdb evolution
```

Then the [tutorial of redis](https://doc.evolution-api.com/v2/pt/requirements/redis) and finally the [docker swarm tutorial](https://doc.evolution-api.com/v2/pt/install/docker) without installing those prerequisites evolution-api can't work.

The evolution.yaml is the final summary of all effort and it's fully working on docker swarm on ubuntu server 24.03.

If your domain changes needs to change the env. variable `SERVER_URL` 
You need `AUTHENTICATION_API_KEY` set here to log-in on evolution-server. 

More on the docs on [Environment Variables](https://doc.evolution-api.com/v2/pt/env)

