# CRM Skynet Provider - SQLite & FastAPI

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.63+-green.svg)](https://fastapi.tiangolo.com/)
[![SQLite](https://img.shields.io/badge/SQLite-3.35+-orange.svg)](https://www.sqlite.org/)
[![Poetry](https://img.shields.io/badge/Poetry-1.1.13+-gold.svg)](https://python-poetry.org/)
[![Docker](https://img.shields.io/badge/Docker-20.10+-blue.svg)](https://www.docker.com/)

## Descrição

Este projeto implementa um sistema de gerenciamento de clientes (CRM) para a Skynet Provider, uma empresa fictícia de telecomunicações. O sistema utiliza um banco de dados SQLite e uma API RESTful construída com FastAPI, oferecendo uma solução eficiente e escalável para gerenciar:

- **Clientes:** Informações de cadastro, contatos e histórico de interações.
- **Planos:** Detalhes dos planos de serviço, preços e velocidades.
- **Contratos:** Ativação, upgrade e histórico de contratos de clientes.
- **Chamados de Suporte:** Abertura, acompanhamento, resolução e histórico de chamados.
- **Faturas e Pagamentos:** Emissão, acompanhamento de pagamentos e histórico financeiro.

## Estrutura do Projeto

```
CRM-Skynet-Provider-SQLite/FastAPI
├── notebooks
├── img
│   └── skynetprovider.png
├── bd
│   └── skynet.db
├── sql
│   └── skynet_v1.sql
├── src
│   └── main.py
└── data
    ├── clientes.csv
    ├── planos.csv
    ├── contratos.csv
    ├── chamados.csv
    ├── atendentes.csv
    ├── historico_atendimento.csv
    ├── faturas.csv
    └── pagamentos.csv

```

**Descrição das Pastas:**

- **notebooks:** Contém notebooks Jupyter para exploração de dados e testes.
- **img:** Armazena imagens utilizadas no projeto, como logotipos e diagramas.
- **bd:** Contém o banco de dados SQLite `skynet.db`.
- **sql:** Armazena scripts SQL para criação e gerenciamento do banco de dados.
- **src:** Contém o código-fonte da API FastAPI, incluindo o arquivo principal `main.py`.
- **data:** Contém arquivos CSV com dados de exemplo para popular o banco de dados.

## Recursos da API

A API RESTful oferece endpoints para realizar operações CRUD em todos os módulos do CRM, incluindo:

- Criação, leitura, atualização e exclusão de clientes.
- Consulta de planos, contratos, chamados de suporte, faturas e pagamentos.
- Geração de boletos e registro de pagamentos.
- Upgrade de planos e criação de novos contratos.
- Monitoramento de métricas e relatórios para os setores financeiro, comercial e de suporte.

## Instalação e Execução

### Modo Tradicional (sem Docker)

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/seu-usuario/CRM-Skynet-Provider-SQLite-FastAPI.git
   ```

2. **Navegue até o diretório do projeto:**

   ```bash
   cd CRM-Skynet-Provider-SQLite-FastAPI
   ```

3. **Instale as dependências com Poetry:**

   ```bash
   poetry install
   ```

4. **Execute a API com Poetry:**

   ```bash
   poetry run uvicorn src.main:app --reload
   ```

5. **Acesse a API:**

   A API estará disponível em `http://localhost:8000` e a documentação interativa em `http://localhost:8000/docs`.

### Implantação com Docker

O projeto também pode ser facilmente implantado usando Docker.

**Pré-requisitos:**

- Docker instalado e em execução.
- Docker Compose instalado.

**Passos para Implantação:**

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/seu-usuario/CRM-Skynet-Provider-SQLite-FastAPI.git
   ```

2. **Navegue até o diretório do projeto:**

   ```bash
   cd CRM-Skynet-Provider-SQLite-FastAPI
   ```

3. **Construa a imagem Docker:**

   ```bash
   docker build -t skynet-crm .
   ```

4. **Execute o contêiner:**

   ```bash
   docker run -p 8000:8000 -v $(pwd)/bd:/app/bd skynet-crm
   ```
   **Observação:** O comando `-v $(pwd)/bd:/app/bd` mapeia o diretório `bd` local para o diretório `/app/bd` dentro do contêiner, garantindo que os dados do banco de dados sejam persistidos.

5. **Acesse a API:**

   A API estará disponível em `http://localhost:8000` e a documentação interativa em `http://localhost:8000/docs`.


## Tecnologias Utilizadas

- **Python:** Linguagem de programação principal.
- **FastAPI:** Framework web para construção da API RESTful.
- **SQLite:** Banco de dados relacional leve e embutido.
- **Pydantic:** Biblioteca para validação de dados e modelagem de objetos.
- **Poetry:** Gerenciador de dependências e ambiente virtual.
- **Docker:** Plataforma para conteinerização de aplicações.

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou pull requests.

## Licença

Este projeto é licenciado sob a licença MIT.
 


