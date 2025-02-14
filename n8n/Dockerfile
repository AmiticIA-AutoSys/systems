FROM n8nio/n8n:latest

# Troca para o usuário root para instalar pacotes
USER root

# Cria o diretório necessário para os nodes personalizados
RUN mkdir -p /home/node/.n8n/nodes

# Define o diretório de trabalho para os nodes personalizados
WORKDIR /home/node/.n8n/nodes

# Instala os pacotes npm necessários
RUN npm install \
    n8n-nodes-vtiger-crm \
    n8n-nodes-evolution-api \
    # Search for details of a Brazilian company using a CNPJ.
    n8n-nodes-cnpj \
    # Complete implementation of ElevenLabs AI voice generation
    n8n-nodes-elevenlabs \
    # FireCrawl nodes
    n8n-nodes-firecrawl-v1 \
    # Allows users to create global constants and use them in all their workflows
    n8n-nodes-globals

# Retorna ao usuário padrão do n8n
USER node