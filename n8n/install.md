### Install

Just docker-compose build then up.

PostgreSQL is installed by default but not redis.

```bash
sudo docker build # custom image by Dockerfile with n8n community nodes
sudo docker compose up -d
```

### Login

Login e-mail is anbidev@gmail.com and password is default.
Since this isn't a paid account or subscription local folder is useless.
Use ctrl+c and ctrl+v from and to JSON text file.

### Community Nodes

Altough the nodes were installed on the custom built docker image they also must be installed on the n8n interface.

Go to Settings->Community Nodes->Install
On the `npm Package Name` set bellow then press Install

- n8n-nodes-vtiger-crm 
- n8n-nodes-evolution-api 




