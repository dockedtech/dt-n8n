# Instalação do n8n com Docker

Este repositório contém os comandos e arquivos de configuração básicos para você preparar seu ambiente e subir sua primeira automação usando o n8n através do Docker, WSL e Linux.

## Acompanhe o Tutorial em Vídeo

Para ver o passo a passo completo e explicações detalhadas, assista ao vídeo no YouTube:
[Instalação do n8n em 10 Minutos no Docker](https://youtu.be/TvOlKTa2Xgk)

---

## n8n de Alta Performance

A configuração deste repositório é ideal para testes, aprendizado e fluxos leves. No entanto, se você precisa de um ambiente robusto e escalável para clientes finais ou automações críticas, uma arquitetura básica pode não ser suficiente.

Para demandas profissionais, você precisará de uma infraestrutura que suporte alto volume de dados sem gargalos, contemplando:

* **PostgreSQL:** Para um banco de dados confiável e de alta performance.
* **Redis:** Para gerenciamento de filas e cache.
* **Workers & Task Runners:** Para escalar o processamento das execuções em paralelo.

**Adquira a infraestrutura completa e pronta para uso:** [n8n de Alta Performance](https://dockedtech.com)

---

## Passo a Passo da Instalação

Siga os comandos abaixo para configurar o ambiente básico demonstrado no [vídeo](https://youtu.be/TvOlKTa2Xgk).

### 1. Preparando o Ambiente no Windows (WSL)

Se você utiliza Windows, instale o Windows Subsystem for Linux (WSL):

```bash
# Instalar o WSL
wsl --install

# Listar distribuições Linux disponíveis
wsl --list --online

# Instalar o Ubuntu (ou outra distribuição de sua escolha)
wsl --install -d Ubuntu-24.04

```

### 2. Preparando o Linux e Instalando o Docker

Acesse o terminal do seu Linux/Ubuntu e atualize os pacotes do sistema:

```bash
sudo apt update

```

Em seguida, instale o Docker utilizando o script oficial:

```bash
curl -fsSL https://get.docker.com | sh

```

### 3. Configurando os arquivos do n8n

Crie o diretório onde os arquivos do servidor irão ficar e acesse-o:

```bash
mkdir n8n-server && cd n8n-server

```

Crie os arquivos de configuração necessários:

```bash
touch docker-compose.yml .env

```

### 4. Arquivo `docker-compose.yml`

Abra o arquivo `docker-compose.yml` criado no passo anterior no seu editor de texto preferido (como o `nano`, `vim` ou `VSCode`) e cole [este código](https://github.com/dockedtech/dt-n8n/blob/main/docker-compose.yml), faça o mesmo com o arquivo `.env` com o [este código](https://github.com/dockedtech/dt-n8n/blob/main/env).

### 5. Gerenciando o Serviço

Para iniciar o n8n e deixá-lo rodando em segundo plano:

```bash
docker compose up -d

```

*Acesse o n8n no seu navegador através de: `https://seu-dominio:5678`

Para parar a execução do n8n:

```bash
docker compose down

```

---
