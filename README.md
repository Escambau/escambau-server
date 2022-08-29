<h1 align="center"> 
  Escambau API 
</h1>

<p align="center">
  Esta API foi criada utilizando json-server para a criação da database e json-server-auth para utilização de tokens JWT
</p>


## Endpoints
 
### Rotas que não precisam de autenticação:

<h2 align ='center'> Cadastro de usuário </h2>

`POST /users - FORMATO DA RESQUISIÇÃO`
```json
{
    "name": "Carlos Mesquita"
    "email": "mesquita@gmail.com",
    "password": "12345"
    "avatarUrl": "https://picsum.photos/200/300/?random"
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
        "avatarUrl": "https://picsum.photos/200/300/?random"
    }
}
```
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
]```

