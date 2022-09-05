<h1 align="center"> 
  Escambau - API 
</h1>

<p align="center">
  Este é o backend da aplicação <strong>Escambau</strong> - Uma plataforma virtual para troca de produtos. O objetivo da aplicação foi planejar, documentar e aplicar os conhecimentos obtidos durante o Módulo 3 da Escola Kenzie, utilizando hard e soft skills com trabalho em equipe.
</p>

<p><strong>Escambau</strong> é um projeto em conjunto dos seguintes membros: 
<ul>
  <li>Allan Salatino</li>
  <li>Carlos Mesquita</li>
  <li>José Ingleson Maciel</li>
  <li>Natália Serrão</li>
  <li>Paula Murta</li>
</p>

<h3> A URL base da API é: https://escambau-api.herokuapp.com </h3>
 
## Rotas que não precisam de autenticação:

<h2 align ='center'> Cadastro de usuário </h2>

`POST /users - FORMATO DA RESQUISIÇÃO`
```json
{
    "name": "Carlos Mesquita",
    "email": "mesquita@gmail.com",
    "password": "12345",
    "avatarUrl": "https://picsum.photos/200/300/?random",
    "cidade": "Manaus ",
    "estado": "AM",
    "cpf": "1239484-44",
    "idade": 22
}
```
<p> Caso dê tudo certo, a resposta será assim: </p>

`POST /users - FORMATO DA RESPOSTA - STATUS 201`
```json
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im1lc3F1aXRhQGdtYWlsLmNvbSIsImlhdCI6MTY2MTgwMjk1NywiZXhwIjoxNjYxODA2NTU3LCJzdWIiOiIyIn0.w4_2qnVK9eNGX8M_4hG3YOUmpJc2YkmPKqx7-M8Kdl0",
    "user": {
        "email": "mesquita@gmail.com",
        "id": 2,
        "password": "12345",
        "avatarUrl": "https://picsum.photos/200/300/?random",
        "cidade": "Manaus ",
        "estado": "AM",
        "cpf": "1239484-44",
        "idade": 22
    }
}
```

<h2 align ='center'> Login </h2>

`POST /login - FORMATO DA RESQUISIÇÃO`
```json
{
    "email": "mesquita@gmail.com",
    "password": "12345"
}
```
<p> Caso dê tudo certo, a resposta será assim: </p>

`POST /login - FORMATO DA RESPOSTA`
```json
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im1lc3F1aXRhQGdtYWlsLmNvbSIsImlhdCI6MTY2MTgwNTQ4MSwiZXhwIjoxNjYxODA5MDgxLCJzdWIiOiIyIn0.gl9O96KY-SPkvgz2qcrkifO6V1bGFuJylnDN9kQKN-I",
    "user": {
        "email": "mesquita@gmail.com",
        "id": 2,
        "avatarUrl": "https://picsum.photos/200/300/?random",
        "cidade": "Manaus ",
        "estado": "AM",
        "cpf": "1239484-44",
        "idade": 22
    }
}
```

<h2 align ='center'> Listagem de produtos </h2>

<p>Nessa aplicação o usuário sem fazer login ou se cadastrar pode ver os produtos cadastrados na plataforma.</p>

`GET /products - FORMATO DA RESPOSTA - STATUS 200 `
```json
[
    {
        "id": 1,
        "name": "Macbook Pro",
        "price": 100,
        "description": "This is product 1",
        "category": "Eletronic",
        "image": "https://picsum.photos/200/300/?random",
        "userId": 1
    },
    {
        "id": 2,
        "name": "Bicicleta Monark",
        "price": 500,
        "description": "This is product 2",
        "category": "Bicycle",
        "image": "https://picsum.photos/200/300/?random",
        "userId": 2
    }
]
```

<h2 align ='center'> Listagem de produtos de um usuário </h2>

`GET /products?userId=2 - FORMATO DA RESPOSTA`
```json
[
    {
        "id": 2,
        "name": "Bicicleta Monark",
        "price": 500,
        "description": "This is product 2",
        "image": "https://picsum.photos/200/300/?random",
        "userId": 2
    }
]
```

## Rotas que precisam de autenticação:

<h2 align ='center'> Cadastro de produto </h2>

`POST /products - FORMATO DA REQUISIÇÃO`
```json
{
    "name": "Iphone Pro Max",
    "price": 800,
    "description": "This is an iphone",
    "image": "https://picsum.photos/200/300/?random",
    "userId": 1
}
```

`POST /products - FORMATO DA RESPOSTA`
```json
{
    "name": "Iphone Pro Max",
    "price": 800,
    "description": "This is an iphone",
    "image": "https://picsum.photos/200/300/?random",
    "userId": 1,
    "id": 3
}
```

<h2 align ='center'> Atualização de produto </h2>

`PUT /products/:id - FORMATO DA REQUISIÇÃO`
```json
{
    "id": 1,
    "name": "Macbook Pro 13",
    "price": 300,
    "description": "This is product 1",
    "image": "https://picsum.photos/200/300/?random",
    "userId": 1
}
```

`PUT /products/:id - FORMATO DA RESPOSTA`
```json
{
    "id": 1,
    "name": "Macbook Pro 13",
    "price": 300,
    "description": "This is product 1",
    "image": "https://picsum.photos/200/300/?random",
    "userId": 1
}
```

<h2 align ='center'> Deletar produto </h2>

`DELETE /products/:id - FORMATO DA REQUISIÇÃO`
```json
{
    "id": 1
}
```
