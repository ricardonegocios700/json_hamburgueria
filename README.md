# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## ENDPOINTS

### Cadastro de usuários

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.
Use o JSON com esses campos obrigatórios:

{
"email": "seu@email.com",
"password": "123456",
"name": "Seu Nome"
}

Retorna o token de autenticação, caso queira encaminhar o usuário direto para o sistema.

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"
{
"email": "seu@email.com",
"password": "suaSenha",
}

### Consulta usuários

GET /users

Não exige envio de dados por JSON.
Lista todos usuários na base de dados
Dispensa autenticação.

Você pode refinar sua consulta usando:

GET /users?name="nomeCompleto"
ou
GET /user?cidade="Osasco"

### Atualizando usuário

PATCH /users/1

Altera dados de um usuário, no exemplo serão alterados dados do usuário com id 1 apenas pelo usuário id.
Exige autenticação.
Envio de dados a serem alterados por JSON, inclua os campos que vc criou ou deseja criar:
{
"email": "seuNovo@email.com",
"password": "novaSenha",
"name": "Correção de Nome",
"cidade": "Osasco"
}

### Remoção de usuário

DELETE /users/1

Não exige envio de dados por JSON.
Exclui um usuário, no exemplo será deletado o usuário com id 1 apenas pelo usuário do id.
Exige autenticação.

### Criar um produto

/POST /products

Use o formato JSON:
{
"name": "Hamburger",
"price": "10.00",
"description": "Hamburger simples",
"image": "url_da_imagem",
"userId": "1"
}

Exige autenticação.

### Consultar todos produtos

/GET /products

Retornará todos os produtos cadastrados

Dispensa uso de JSON.
Dispensa autenticação.

### Consulta refinada de produtos

/GET /products?name=Hamburger

Retornará todos os produtos cadastrados cujo campo name sejam idênticos à Hamburger, caso queira encontra com mais detalhes, por exemplo com preço = 10,00 use:

/GET /products?name=Hamburger?price=10.00
Lembre-se que o DB usa formato americano de numeração.

Dispensa uso de JSON.
Dispensa autenticação.

### Atualizar um produto

/PATCH /products/1
Lembre-se que o nr 1 indica o id do produto a ser alterado.

Use o formato JSON:
{
"name": "Hamburger",
"price": "10.00",
"description": "Hamburger simples",
"image": "url_da_imagem"
}

Exige autenticação.

### Deletar um produto

/DELETE /products/1
Lembre-se que o nr 1 indica o id do produto a ser deletado.

Dispensa uso de JSON.
Exige autenticação.

### Adicionar ao carrinho

/POST /cart

Use item selecionado no produto, que terá o seguinte formato:
{
"name": "Hamburger",
"price": "10.00",
"description": "Hamburger simples",
"image": "url_da_imagem",
"userId": "1"
"id": 1
}

Exige autenticação.

### Consultar o carrinho

/GET /cart

Retornará todos os produtos no carrinho.

Dispensa uso de JSON.
Exige autenticação.

### Consulta refinada no carrinho

/GET /cart?name=Hamburger

Retornará todos os produtos no carrinho cujo campo name sejam idênticos à Hamburger, caso queira encontra com mais detalhes, por exemplo com preço = 10,00 use:

/GET /cart?name=Hamburger?price=10.00
Lembre-se que o DB usa formato americano de numeração.

Dispensa uso de JSON.
Exige autenticação.

### Atualizar um carrinho

/PATCH /cart/1
Lembre-se que o nr 1 indica o id do produno no carrinho a ser alterado.

Use o formato JSON:
{
"name": "Hamburger",
"price": "10.00",
"description": "Hamburger simples",
"image": "url_da_imagem"
}

Exige autenticação.

### Deletar um carrinho

/DELETE /cart/1
Lembre-se que o nr 1 indica o id do carrinho a ser deletado.

Dispensa uso de JSON.
Exige autenticação.
