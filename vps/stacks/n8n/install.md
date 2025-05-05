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

#### For a fresh install

Use the Portainer-> Volumes interface. On the `n8n_n8n_data` upload the custom nodes *.tgz files to the nodes folder. 
Then run bellow to install everything you need then refresh (reboot containers) the n8n stack.

```bash
# npm package directory for everything n8n loads
mkdir -p /home/node/.n8n/nodes
cd /home/node/.n8n/nodes

# Install node packages for javascript **Code Node**
# and install node packages of n8n **Custom Nodes** developed by me
# For n8n everything is a node package THERE IS NO DIFFERENCE!
# Note: never install on /home/node/.n8n/custom that's for development only
# would work why mixing development with production? don't mess with the things!
npm install \
    # some npm standards     
    # date and time library
    moment \ 
    # utility library
    lodash \
    # promise based HTTP client 
    axios \
    # chatwoot node
    @devlikeapro/n8n-nodes-chatwoot \    
    # n8n nodes community nodes
    n8n-nodes-vtiger-crm \
    n8n-nodes-evolution-api \
    # Search for details of a Brazilian company using a CNPJ.
    n8n-nodes-cnpj \
    # Complete implementation of ElevenLabs AI voice generation
    n8n-nodes-elevenlabs \
    # FireCrawl nodes
    n8n-nodes-firecrawl-v1 \
    # Allows users to create global constants and use them in all their workflows
    n8n-nodes-globals \
    # Auvo API
    ./n8n-nodes-auvoapi-*.tgz \    
    # Vtigerx
    ./n8n-nodes-vtigerx-*.tgz 
```

#### Not fresh install 

Use the Portainer-> Volumes interface. On the `n8n_n8n_data` upload the custom nodes *.tgz and run npm.
Then reboot (Refresh) the stack and DONE.