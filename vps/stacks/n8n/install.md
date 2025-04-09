### Build Dockerfile

```bash
sudo su # only works pushing with roo
docker login -u eusoubrasileiro
# use dockerhub access token
docker build . -t eusoubrasileiro/n8n
# modify the tag:1.0 for whatever value you see fit
docker tag eusoubrasileiro/n8n eusoubrasileiro/n8n:1.0
docker push eusoubrasileiro/n8n:1.0
```

### Install

##### 1. Install Redis 

For RAM caching (astraweb n8n workers model)

> Distributed Processing Architecture: Redis serves as the message broker in a multi-instance setup, where one main n8n instance handles triggers and webhook calls while multiple worker instances perform the actual workflow executions.
> Horizontal Scaling: This architecture allows you to scale up by adding more workers or scale down by removing them as your workload demands change.
> Improved Throughput: n8n can handle up to 220 workflow executions per second on a single instance, but with Redis-enabled queue mode, you can significantly increase this capacity by adding more worker instances.
> Process Flow Optimization: The main instance passes execution IDs to Redis, which maintains the queue of pending executions and allows workers to pick them up efficiently.

##### 2. Create the database "n8n" on postgresql service using pgadmin.
##### 3. Use portainer and load the *.yaml

Todo: take a look on astraweb for superior implementation with workers and splitting editor from the rest. 

### Community Nodes

Altough the nodes were installed on the custom built docker image they also must be installed on the n8n interface.

Go to Settings->Community Nodes->Install
On the `npm Package Name` set bellow then press Install

- n8n-nodes-vtiger-crm 
- n8n-nodes-evolution-api 
- ... etc 