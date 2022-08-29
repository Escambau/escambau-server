<h1 align="center"> 
  Escambau API 
</h1>

<p align="center">
  Esta API foi criada utilizando json-server para a criação da database e json-server-auth para utilização de tokens JWT
</p>
 
## Rotas que não precisam de autenticação:

<h2 align ='center'> Cadastro de usuário </h2>

`POST /users - FORMATO DA RESQUISIÇÃO`
```json
{
    "name": "Carlos Mesquita"
    "email": "mesquita@gmail.com",
    "password": "12345"
    "avatarUrl": "https://picsum.photos/200/300/?random",
    "endereço": "Rua 0 ",
    "cpf": "1239484-44",
    "idade": 22
}
```

`POST /users - FORMATO DA RESPOSTA`
```json
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im1lc3F1aXRhQGdtYWlsLmNvbSIsImlhdCI6MTY2MTgwMjk1NywiZXhwIjoxNjYxODA2NTU3LCJzdWIiOiIyIn0.w4_2qnVK9eNGX8M_4hG3YOUmpJc2YkmPKqx7-M8Kdl0",
    "user": {
        "email": "mesquita@gmail.com",
        "id": 2,
        "password": "12345",
        "avatarUrl": "https://picsum.photos/200/300/?random",
        "endereço": "Rua 0 ",
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

`POST /login - FORMATO DA RESPOSTA`
```json
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im1lc3F1aXRhQGdtYWlsLmNvbSIsImlhdCI6MTY2MTgwNTQ4MSwiZXhwIjoxNjYxODA5MDgxLCJzdWIiOiIyIn0.gl9O96KY-SPkvgz2qcrkifO6V1bGFuJylnDN9kQKN-I",
    "user": {
        "email": "mesquita@gmail.com",
        "id": 2,
        "avatarUrl": "https://picsum.photos/200/300/?random",
        "endereço": "Rua 0 ",
        "cpf": "1239484-44",
        "idade": 22
    }
}
```

<h2 align ='center'> Listagem de produtos </h2>

`GET /products - FORMATO DA RESPOSTA`
```json
[
    {
        "id": 1,
        "name": "Macbook Pro",
        "price": 100,
        "description": "This is product 1",
        "image": "https://picsum.photos/200/300/?random",
        "userId": 1
    },
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
