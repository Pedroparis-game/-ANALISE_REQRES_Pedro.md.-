Documentação de Análise da API - ReqRes - Elias

    Cenário A: Listar Utilizadores da Página 2

Verbo HTTP: GET
URL Completa: https://reqres.in/api/users?page=2
Body da Requisição: Nenhum
Status Code Esperado: 200 OK
Resposta da API (Exemplo do JSON):
{
"page": 2,
"per_page": 6,
"total": 12,
"total_pages": 2,
"data": [
{
"id": 7,
"email": "michael.lawson@reqres.in",
"first_name": "Michael",
"last_name": "Lawson",
"avatar": "https://reqres.in/img/faces/7-image.jpg"
}
]
}

    Cenário B: Criar Novo Utilizador

Verbo HTTP: POST
URL Completa: https://reqres.in/api/users
Body da Requisição:
{
"name": "Elias",
"job": "dev front end"
}
Status Code Esperado: 201 Created
Resposta da API (Exemplo do JSON):
{
"name": "Elias",
"job": "dev front end",
"id": "276",
"createdAt": "2026-07-03T22:53:43.412Z"
}

    Cenário C: Utilizador Inexistente

Verbo HTTP: GET
URL Completa: https://reqres.in/api/users/26
Body da Requisição: Nenhum
Status Code Esperado: 404 Not Found
Resposta da API (Exemplo do JSON):
{}
