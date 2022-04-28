# Api de games
Este é uma documentação exemplo de api de games desenvolvido em aprendizado.
## Endpoints
### GET /games
Este endpoit serve para retornar todos os games cadastrado no banco de dados.
#### Parametros
Nenhum
### Respostas
#### Ok! (200)
Esta resposta indica que você vai receber a listagem com sucesso

Exemplo de resposta:
```
[
    {
        "id": 2,
        "title": "FIFA 2019",
        "year": 2019,
        "price": 400,
        "createdAt": "2022-04-20T13:36:30.000Z",
        "updatedAt": "2022-04-25T20:30:41.000Z"
    },
    {
        "id": 36,
        "title": "Forza",
        "year": 2000,
        "price": 21,
        "createdAt": "2022-04-25T20:01:55.000Z",
        "updatedAt": "2022-04-25T20:01:55.000Z"
    }
]
```
#### Erro no servidor (500)
Esta resposta indica que há um erro no servidor
### GET /game/:id
Este endpoit serve para retornar o game pelo id.
#### Parametros
Nenhum
### Respostas
#### Ok! (200)
Esta resposta indica que vai listar o game peddio

Exemplo de resposta:
```
{
    "id": 36,
    "title": "Forza",
    "year": 2000,
    "price": 21,
    "createdAt": "2022-04-25T20:01:55.000Z",
    "updatedAt": "2022-04-25T20:01:55.000Z"
}
```
#### Erro no servidor (500)
Esta resposta indica que há um erro no servidor
#### Erro no servidor (404)
Esta resposta indica que o game nao foi encontrado, possível não exitir ou ser NULL
#### Erro no servidor (400)
Esta resposta indica que o a requisição foi inválida  
### POST /game
Este endpoit serve para um novo cadastro de game.
#### Parametros
```
title: Titulo do game (STRING)
year: Ano do lançamento do game (INTEGER)
price Preço do game (FLOAT)
```
Exemplo dos parametros
```
{
    title: "Forza",
    year: 2000,
    price: 21
}
```
### Respostas
#### Criado! (201)
Esta resposta indica que o game foi cadastrado com sucesso.
#### Erro no servidor (500)
Esta resposta indica que há um erro no servidor
### DELETE /game/:id
Este endpoit serve para deletar o game pelo id.
#### Parametros
Nenhum
### Respostas
#### Criado! (200)
Esta resposta indica que o game foi deletado com sucesso.
#### Erro no servidor (404)
Esta resposta indica que o game nao foi encontrado, possível não exitir ou ser NULL
### PUT /game/:id
Este endpoit serve para editar o game pelo id.
#### Parametros
```
title: Titulo do game (STRING)
year: Ano do lançamento do game (INTEGER)
price Preço do game (FLOAT)
```
Exemplo dos parametros:
```
{
    title : "Forza",
    year : 2000,
    price: 80,
}
```
### Respostas
#### Ok! (200)
Esta resposta indica que o game foi atualizado
#### Erro no servidor (404)
Esta resposta indica que o game nao foi encontrado, possível não exitir ou ser NULL
### POST /auth
Este endpoit serve para gerar um token para o usuário.
#### Parametros
```
email: email do usuario
password: senha do usuario
```
Exemplo dos parametros:
```
{
    "email" : "email@email.com",
    "password" : "1234"
} 
```
### Respostas
#### Ok! (200)
Esta resposta indica que o token foi gerado.

Exemplo de resposta:
```
{
    "token": "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJlbWFpbEBlbWFpbC5jb20iLCJpYXQiOjE2NTExODUwNTgsImV4cCI6MTY1MTM1Nzg1OH0.b7fk14kQTvKTFbXQ1XtF2GkZrsFwHiiDgn1EMIQVVwg"
}
```
#### Erro no servidor (404)
Esta resposta indica que o usuario nao foi encontrado.

#### Erro no servidor (400)
Esta resposta indica que houve problema no servidor.
