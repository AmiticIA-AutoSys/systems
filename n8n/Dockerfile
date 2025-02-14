FROM n8nio/n8n:latest

# Troca para o usuário root para instalar pacotes
USER root

# Cria o diretório necessário para os nodes personalizados
RUN mkdir -p /home/node/.n8n/nodes

# Define o diretório de trabalho para os nodes personalizados
WORKDIR /home/node/.n8n/nodes

# Instala os pacotes npm necessários
RUN npm install n8n-nodes-vtiger-crm n8n-nodes-evolution-api

# Retorna ao usuário padrão do n8n
USER node