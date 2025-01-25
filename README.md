# wazuh-docker-tutorial
Tutoriais e procedimentos para instalar o Wazuh via Docker.

## Instalação do Wazuh Usando Docker

### Instale o Docker no seu servidor Linux
Execute o seguinte comando para instalar o Docker de maneira simples e rápida:

```bash
curl -fsSL https://get.docker.com -o get-docker.sh && sh get-docker.sh
```

### Clone o repositório do Wazuh Docker
Certifique-se de baixar a versão desejada. No exemplo abaixo, estamos usando a versão v4.10.1:

```bash
git clone https://github.com/wazuh/wazuh-docker.git -b v4.10.1
```

### Entre no diretório apropriado
Navegue para o diretório `wazuh-docker/single-node` para configurar o ambiente:

```bash
cd wazuh-docker/single-node
```

### Gere os certificados necessários
Execute o comando abaixo para gerar os certificados que o Wazuh Indexer precisa:

```bash
docker compose -f generate-indexer-certs.yml run --rm generator
```

### Suba os contêineres do Wazuh
Inicie o Wazuh com o seguinte comando:

```bash
docker compose up -d
```

Pronto! O Wazuh já está instalado e funcionando no seu servidor. Agora você pode acessar o dashboard e configurar os agentes.

