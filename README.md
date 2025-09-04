# AllBooks - Loja Virtual com API Mock

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![JSON Server](https://img.shields.io/badge/JSON--Server-7d467d?style=for-the-badge)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)

Este repositório contém dois componentes principais:

1.  **AllBooks**: O front-end de um MVP (Minimum Viable Product) de uma loja virtual para venda de livros da Casa do Código.
2.  **API Mock**: Uma API RESTful para dar suporte ao front-end, construída com **JSON Server** e autenticação via **JSON Web Tokens (JWT)**.

---

## 📚 Sobre o Projeto AllBooks

O AllBooks é o conceito de uma loja virtual focada em livros. Como um MVP, ele representa a base inicial do projeto, com muitas funcionalidades planejadas para o futuro. A API mockada serve para simular o comportamento de um back-end real, permitindo o desenvolvimento e teste de funcionalidades como cadastro, login e acesso a rotas protegidas.

---

## ⚙️ API Mock (JSON Server + JWT Auth)

Esta é uma API mock que simula um serviço de back-end real, com persistência de dados em um arquivo `db.json` e um sistema de autenticação seguro.

### 1. Instalação e Execução

Para iniciar o servidor da API localmente, siga os passos:

```bash
# 1. Instale as dependências do projeto
npm install

# 2. Inicie o servidor com o middleware de autenticação
npm run start-auth

2. Como se Registrar
Para criar um novo usuário, envie uma requisição POST para o endpoint público de registro.

Endpoint: POST http://localhost:8000/public/registrar

Corpo da Requisição (Body):

JSON

{
    "nome": "michael marin",
    "email": "michael@teste.com",
    "senha": "123456",
    "endereco": "Rua teste, 1234",
    "complemento": "Vila dos testes",
    "cep": "0101010-000"
}
Nota: O campo email é único. Tentativas de registrar um e-mail já existente resultarão em erro.

3. Como Fazer Login
Após o registro, você pode autenticar o usuário para obter um token de acesso.

Endpoint: POST http://localhost:8000/public/login

Corpo da Requisição (Body):

JSON

{
  "email": "michael@teste.com",
  "senha": "123456"
}
A resposta conterá o token de acesso e os dados do usuário.

Resposta:

JSON

{
   "access_token": "<SEU_ACCESS_TOKEN>",
   "user": {
      "nome": "michael marin",
      "email": "michael@teste.com",
      "id": 1
      ...
   }
}
4. Autenticando Requisições Futuras
Para acessar rotas protegidas da API, você deve incluir o access_token no cabeçalho (Header) de autorização de todas as suas próximas requisições.

Header:

Authorization: Bearer <SEU_ACCESS_TOKEN>
