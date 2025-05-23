# Estudo de Node.js: API de Vídeos com Fastify e PostgreSQL por Dionys Eicholz

Este projeto é um estudo prático de desenvolvimento backend com Node.js, utilizando o framework Fastify para criar uma API RESTful para gerenciar vídeos. A aplicação se conecta a um banco de dados PostgreSQL (configurado para uso com NeonDB) para persistência de dados.

## ✨ Funcionalidades

* **CRUD de Vídeos:**
    * Criar um novo vídeo (POST /videos)
    * Listar todos os vídeos (GET /videos)
    * Listar vídeos filtrando por título (GET /videos?search=...)
    * Atualizar um vídeo existente (PUT /videos/:id)
    * Deletar um vídeo (DELETE /videos/:id)

## 🛠️ Tecnologias Utilizadas

* **Backend:** Node.js
* **Framework:** Fastify
* **Banco de Dados:** PostgreSQL (com NeonDB serverless)
* **ORM/Driver BD:** `postgres` (node-postgres) e `@neondatabase/serverless` para conexão.
* **Gerenciamento de Ambiente:** `dotenv`
* **Utilitários:**
    * `crypto` (para `randomUUID`)

## 📋 Pré-requisitos

* **Node.js:** Versão 18.x ou superior (o projeto usa `type: "module"` e importações ES6).
* **NPM** (geralmente vem com o Node.js).
* **VS Code** (opcional, mas recomendado) com a extensão **REST Client** (por Huachao Mao) para testar as requisições.

## ⚙️ Configuração Inicial

1.  **Clone o Repositório:**
    ```bash
    git clone <URL_DO_SEU_REPOSITORIO>
    cd <NOME_DA_PASTA_DO_PROJETO>
    ```

2.  **Instale as Dependências:**
    ```bash
    npm install
    ```
    Este comando instalará todas as dependências listadas no arquivo `package.json`.

3.  **Configure as Variáveis de Ambiente:**
    * Crie um arquivo chamado `.env` na raiz do projeto.
    * Adicione a seguinte variável de ambiente ao arquivo `.env`, substituindo pelo seu valor real da URL de conexão do NeonDB (ou outro PostgreSQL):
        ```env
        DATABASE_URL="postgresql://user:password@host:port/dbname?sslmode=require"
        ```
        Esta variável é utilizada pelo `db.js` para conectar ao banco de dados PostgreSQL.

4.  **Crie a Tabela no Banco de Dados:**
    * Após configurar o `.env` com a `DATABASE_URL` correta, execute o script para criar a tabela `videos` no seu banco de dados:
        ```bash
        node create-table.js
        ```
        Você deverá ver a mensagem "Tabela criada" no console se tudo ocorrer bem. Este script utiliza a conexão configurada em `db.js`.

## 🚀 Executando a Aplicação

Para iniciar o servidor da API:

```bash
npm run dev
