### From docs 

https://www.chatwoot.com/docs/self-hosted/deployment/docker


#### To run 

```bash 
docker compose run --rm rails bundle exec rails db:chatwoot_prepare
docker compose up -d
```