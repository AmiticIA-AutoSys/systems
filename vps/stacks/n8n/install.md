### Build

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

Use portainer 

### Community Nodes

Altough the nodes were installed on the custom built docker image they also must be installed on the n8n interface.

Go to Settings->Community Nodes->Install
On the `npm Package Name` set bellow then press Install

- n8n-nodes-vtiger-crm 
- n8n-nodes-evolution-api 
- ... etc 