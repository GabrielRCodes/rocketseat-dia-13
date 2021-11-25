HTTP = HyperText Transfer Protocol - Protocolo de Transferênciade HyperTexto

- Permite troca de informações e dados na internet
- Uma troca de mensagens
- HTML, CSS, Scripts, Imagens, Vídeos
- Uma chamada para cada um desses recursos

Status codes:

- 100 = CONTINUE
- 200 = OK
- 201 = Criação de conteúdo
- 204 = Recebe a pesquisa, mas não é um conteúdo
- 300 = Movido
- 301 = Movido permanentemente
- 308 = Redirecionado permanentemente
- 302 = Encontrado
- 307 = Temporariamente redirecionado
- 400 = Bad request
- 401 = Não autorizado
- 403 = Sem permissão | Forbidden
- 404 = Página não encontrada, recurso não encontrado
- 429 = Muitos requests
- 500 = Erro de programação | Internal Server Error
- 503 = Serviço indisponível

CURL
(TERMINAL)

- man curl
- curl <URL>
- curl -v <URL>
- curl -i <URL>
- curl -I <URL>
- ccat db.json (coletar informações do arquivo)

PORTAS IMPLICITAS (DEFAULT):

- https = 443
- http = 80

METHODS:

- OPTIONS
- GET
- HEAD
- POST
- PUT
- PATCH
- DELETE

Como instalar JSON Server
npm install -g json-server

O -g é para instalar de uma maneira global na máquina.

- mkdir <nome>
  EX: http-course

- cd <nome>
  EX: http-course

- vim <nome> | Para criar o arquivo
  EX: db.json

  COLAR DENTRO:

  {
  "posts": [
  { "id": 1, "title": "json-server", "author": "typicode" }
  ],
  "comments": [
  { "id": 1, "body": "some comment", "postId": 1 }
  ],
  "profile": { "name": "typicode" }
  }

- TECLA ESC
- :wq
  = Sair do vim

Iniciar servidor:
-> json-server --watch db.json

CTRL + SHIFT + T = Abre nova aba do terminal

curl http://localhost:3000/posts

OPTIONS: "Informações sobre a disponibilidade da requisição"
-> curl -X OPTIONS http://localhost:3000/posts -i

GET: "Pegar um recurso" - "Somente recebe dados" "Recebe BODY"
-> curl -v // curl -i

HEAD: "Semelhante ao get, porém recebe somente o cabeçalho"
-> curl -I http://localhost:3000/posts

POST: "Publicar / Cadastrar um recurso" - "Serve somente para criar"
-> curl -d '{ "id": 2, "title": "json-server-2", "author": "gabrielrcodes" }' -H "Content-type: application/json" -X POST http://localhost:3000/posts

-> -H = editar header

-> Não é idempotente, a resposta é alterada

PUT: "Criar um novo recurso ou atualizar um recurso"
-> curl -d '{"name": "gabriel"}' -H 'Content-type: application/json' -X PUT http://localhost:3000/profile

-> -i = para ver o body

PATCH: "Modificação parcial de um recurso" - "ALTERA APENAS UMA PARTE DO RECURSO"
-> curl -d '{"title": "my-title"}' -H "Content-type: application/json" -X PATCH http://localhost:3000/posts/1

DELETE: "REMOVER UM RECURSO"
-> curl -X DELETE http://localhost:3000/posts/2

- 2 = ID DO RECURSO DELETADO

HEADERS: "Informações adicionais para o pedido ou resposta"
-> Contextos:

- General
- Request
- Response

ACESSAR POR:

- Navegador
- Inspecionar elementos
- Network
- Headers

-> Nome: valor

ONDE CONSEGUIR INFORMAÇÕES? devdocs.io
