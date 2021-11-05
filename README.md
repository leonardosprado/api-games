# API DE GAMES
Esta API é utilizada para TAL E TAL 

## Endpoints
### GET /games
Esse endpoint é responsãvel por retornar a listagem de todos os games cadastrado no banco de dados 
#### Parametros
Nenhum
#### Repostas
##### OK! 200
Caso essa resposta aconteça, você vai receber a listagem de todos os games.

Exemplo de resposta: 
```
[
    {
        "id": 65,
        "title": "Sea of thieves",
        "year": "1234",
        "price": "40"
    },
    {
        "id": 2,
        "title": "Minicraft",
        "year": 2012,
        "price": 20
    },
    {
        "id": 2323,
        "title": "GTA SAN ANDREAS",
        "price": "120",
        "year": "2002"
    }
]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processe de autenticação. Motivos: Token inválido, Token expirado

Exemplo de resposta: 
```
{
    "err": "Token invalido"
}
```


### POST /auth
Este endpoint é responsãvel por fazer o processo de login. 
#### Parametros
email: E-mail do usuário cadastrado no sistema.

senha: Senha cadastrada no sistema, com aquele determinado email.

```
{
    "email":"65415708090",
    "senha":"690910"
}
```
#### Repostas
##### OK! 200
Caso essa resposta aconteça, você vai receber o token JWT para acessar endpoints protegidos na API.

Exemplo de resposta: 
```
{
      "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjEiLCJlbWFpbCI6Imxlb25hcmRvcHJhZG8xOUBnbWFpbC5jb20iLCJpYXQiOjE2MzYxMzI0MTgsImV4cCI6MTYzNjMwNTIxOH0.ktoEjyVL9zTH51Ujl9SGpu3ooBXXbFS-FilLf5oPk5k"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processe de autenticação. Motivos: Senha ou Email incorreto.

Exemplo de resposta: 
```
{
    err:"Crecendiais inválidas!"
}
```
