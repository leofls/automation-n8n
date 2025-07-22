# Guia de Execução e Configuração do projeto

## Pré-requisitos
- [Docker](https://www.docker.com/)

## Instalação

```bash
git clone git@github.com:leofls/automation-n8n.git
```
ou 
```bash
git clone https://github.com/leofls/automation-n8n.git
```    

## Executando o Projeto

### Usando Docker

```bash
docker-compose up
```

## Configuração

### Crie uma uma network para o Docker:

```bash
docker network create n8n-network
``` 
E altere o arquivo `docker-compose.yml` para usar essa rede:
```yaml
networks:
    n8n-network:
        external: true
```

Certifique de que o Docker esteja rodando e que a rede `n8n-network` foi criada com sucesso.

### Configure as variáveis de ambiente
Crie um arquivo `.env` na raiz do projeto com as variáveis necessárias. 
```shell
cp .env.example .env
```

Exemplo:

```env
DB_TYPE=postgresdb
DB_POSTGRESDB_HOST=localhost
DB_POSTGRESDB_PORT=5432
DB_POSTGRESDB_DATABASE=n8n
DB_POSTGRESDB_USER=usuario
DB_POSTGRESDB_PASSWORD=senha
N8N_BASIC_AUTH_ACTIVE=true
N8N_BASIC_AUTH_USER=admin
N8N_BASIC_AUTH_PASSWORD=admin123
```

lembre-se de substituir os valores acima pelos seus dados reais.


## Acessando a Interface

Abra [http://localhost:5678](http://localhost:5678) no navegador.

## Referências

- [Documentação oficial do n8n](https://docs.n8n.io/)
- [Configuração via Docker](https://docs.n8n.io/hosting/docker/)
