# Docker

## Gerenciamento de Containers
```bash
# Executar um container
docker run [opções] nome_da_imagem

# Listar containers em execução
docker ps

# Listar todos os containers (incluindo parados)
docker ps -a

# Parar um container
docker stop nome_ou_id_do_container

# Iniciar um container parado
docker start nome_ou_id_do_container

# Remover um container
docker rm nome_ou_id_do_container
```

## Gerenciamento de Imagens

```bash
# Baixar uma imagem
docker pull nome_da_imagem

# Listar imagens locais
docker images

# Remover uma imagem
docker rmi nome_da_imagem
```

## Docker Compose

Para orquestrar múltiplos containers, crie um `docker-compose.yml`:

```yaml
version: '3'
services:
  web:
    build: .
    ports:
      - "3000:3000"
  db:
    image: postgres
    environment:
      POSTGRES_PASSWORD: exemplo
```

## Como usar

Inicie os containers:

```bash
docker-compose up -d
```

Acesse o container

```bash
docker exec -it container_name bash
```

## Comandos úteis
- Ver logs: `docker logs container_name`
- iniciar os containers: `docker-compose up -d`
- Parar os containers: `docker-compose down`
- Reiniciar os containers: `docker-compose restart`
- Parar e remover volumes: `docker-compose down -v`
