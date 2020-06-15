# api-de-games-docs
esta api e utilizada para cadastro de qualquer produto
## Endpoints
### GET /games
Esse endpoint e responsavel por retornar a listagem de todos games cadastrados no banco de dados.
#### Parametros
Nenhum
#### Respostas
##### Ok ! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.

Exemplo de resposta:
```
[
    {
        "id": 23,
        "title": "Good OF War",
        "year": 2019,
        "price": 60
    },
    {
        "id": 75,
        "title": "Star Wars",
        "year": 2019,
        "price": 90
    },
    {
        "id": 3,
        "title": "Call Of Duty",
        "year": 2019,
        "price": 75
    },
    {
        "id": 2323,
        "title": "poo",
        "price": "89.00",
        "year": "2019"
    }
]


```
##### Falha na Autenticação ! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos : Senha o email incorreto: 

Exemplo de resposta:
```
{
    {err: "Credencial invalida!"}
}

```

### POST/auth
Esse endpoint e responsavel por retornar fazer o processo de login.
#### Parametros
email: E-mail do usuario cadastrado no sistema.

password: Senha do usuario cadastrado no sistema, com aquele determinado email.

Exemplo:
```
{
	"email":"silva@gmail.com",
	"password":"wer43>"
} 
```
#### Respostas
##### Ok ! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de resposta:
```
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MiwiZW1haWwiOiJzaWx2YUBnbWFpbC5jb20iLCJpYXQiOjE1OTIxODcxODYsImV4cCI6MTU5MjM1OTk4Nn0.dHgfWQeTGiMfwyR_uCxWUFeyznAlAZU-BCi1JkgEBz4"
}
 
```
##### Falha na Autenticação ! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos : token invalido, token expirado.

Exemplo de resposta:
```
{
    "err": "TOKEN INVALIDO!"
}

```
