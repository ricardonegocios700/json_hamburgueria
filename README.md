# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### Cadastrando seus parentes

POST /familiares

Visando trabalhar sua àrvore genealógica você pode cadastrar seus parentes:
{
"nome": "Valquiria",
"parentesco": "irmão",
"ancestralidade": "paterna",
"userId": //seu id
}

### Alterar um parente

PATCH /familiares/id
onde id é nr do parente no banco de dados

Permite alterar dados cadastrados de seu parente com determinado id
{
"ancestralidade": "materna"
}

### Para ver todos parentes

GET /familiares
Retorna todos os parentes registrados

### Para ver meus parentes

GET /familiares?userId=id
onde id é seu número no banco de dados

### Para ver meus parentes de um tipo especifico

GET /familiares?userId=id&&parentesco=tipo
onde id é nr do usuário no banco de dados
onde tipo é uma classificação no banco de dados

### Cadastrando seus amigos

POST /amigos

Visando trabalhar sua àrvore genealógica você pode cadastrar seus amigos:
{
"nome": "Ailton",
"nivel": "grande amigo",
"userId": //seu id
}

### Alterar um amigo

PATCH /amigos/id
onde id é nr do amigo no banco de dados

Permite alterar dados cadastrados de seu amigo com determinado id
{
"nivel": "colega"
}

### Para ver todos amigos

GET /amigos
Retorna todos os amigos registrados

### Para ver meus amigos

GET /amigos?userId=id
onde id é seu número no banco de dados

### Para ver meus amigos de um tipo especifico

GET /amigos?userId=id&&nivel=tipo
onde id é nr do usuário no banco de dados
onde tipo é uma classificação no banco de dados
