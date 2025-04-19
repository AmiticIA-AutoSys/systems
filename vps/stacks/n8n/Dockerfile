FROM n8nio/n8n:1.84.0

USER root

# npm package directory for everything n8n loads
RUN mkdir -p /home/node/.n8n/nodes

# Define the working directory 
WORKDIR /home/node/.n8n/nodes

# Copy .tgz files into the image
COPY n8n-nodes-auvoapi-*.tgz .
COPY n8n-nodes-vtigerx-*.tgz .

# Install node packages for javascript **Code Node**
# and install node packages of n8n **Custom Nodes** developed by me
# For n8n everything is a node package THERE IS NO DIFFERENCE!
# Note: never install on /home/node/.n8n/custom that's for development only
# would work but would be a mess
RUN npm install \
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

# Retorna ao usuário padrão do n8n
USER node



