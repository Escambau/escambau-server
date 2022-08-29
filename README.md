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
`POST /products - FORMATO DA RESQUISIÇÃO`

