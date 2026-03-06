# Node.js Order API

API REST para gerenciamento de pedidos e itens desenvolvida com **Node.js**, **Express** e **MySQL**.

Este projeto foi desenvolvido como parte de um **teste técnico de backend**, com o objetivo de demonstrar conhecimentos em construção de APIs, integração com banco de dados relacional e manipulação de dados entre entidades relacionadas.

---

## 🚀 Tecnologias utilizadas

- Node.js
- Express
- MySQL
- dotenv
- cors

---

## 📂 Estrutura do projeto


nodejs-order-api
│
├── server.js
├── package.json
├── .env
└── README.md


---

## ⚙️ Configuração do banco de dados

Criar o banco:

```sql
CREATE DATABASE order_api;
USE order_api;

Criar tabela de pedidos:

CREATE TABLE orders (
    orderId VARCHAR(50) PRIMARY KEY,
    value DECIMAL(10,2),
    creationDate DATETIME
);

Criar tabela de itens:

CREATE TABLE items (
    id INT AUTO_INCREMENT PRIMARY KEY,
    orderId VARCHAR(50),
    productId INT,
    quantity INT,
    price DECIMAL(10,2),
    FOREIGN KEY (orderId) REFERENCES orders(orderId)
);
▶️ Como executar o projeto
1️⃣ Instalar dependências
npm install
2️⃣ Configurar variáveis de ambiente

Criar arquivo .env

DB_HOST=localhost
DB_USER=root
DB_PASSWORD=sua_senha
DB_NAME=order_api
PORT=3000
3️⃣ Iniciar o servidor
node server.js

Servidor irá rodar em:

http://localhost:3000
📡 Endpoints da API
Criar pedido

POST

/order

Exemplo de requisição:

{
  "numeroPedido": "1001",
  "valorTotal": 200,
  "dataCriacao": "2026-03-06T12:00:00Z",
  "items": [
    {
      "idItem": 1,
      "quantidadeItem": 2,
      "valorItem": 100
    }
  ]
}
Buscar pedido

GET

/order/:id

Exemplo:

/order/1001

Resposta:

{
  "order": [
    {
      "orderId": "1001",
      "value": 200
    }
  ],
  "items": [
    {
      "productId": 1,
      "quantity": 2,
      "price": 100
    }
  ]
}
🎯 Objetivo do projeto

Demonstrar conhecimentos em:

Desenvolvimento de APIs REST

Integração com banco de dados MySQL

Estruturação de backend com Node.js

Manipulação de dados entre pedidos e itens

👨‍💻 Autor

Roberson de Oliveira
