# 🚀 Desafio Prático: Engenharia de Requisitos e Análise de API

**Instituição:** SENAC Passo Fundo  
**Curso:** Técnico em Desenvolvimento de Sistemas (TDS)  
**Unidade Curricular:** Analisar Orientações Técnicas  
**Ferramentas:** Navegador, Hoppscotch.io (ou Postman) e Git/GitHub.

---  

## 🏢 O Cenário (Contexto de Mercado)

Vocês foram recém-contratados como Analistas de Sistemas Júnior numa *Software House*. O Tech Lead da vossa equipa informou que o Front-end precisa ser conectado ao novo sistema de gestão de utilizadores. O Back-end já terminou de programar a API e entregou-vos a documentação técnica.

**A regra de ouro:** Antes de escrever uma única linha de código no Front-end, um bom analista deve ler o "contrato" da API, testar as rotas e documentar as regras de negócio encontradas.

---

## 🎯 A Vossa Missão

Vocês devem aceder ao repositório de testes oficial da nossa API em **[https://reqres.in/](https://reqres.in/)**. A vossa missão é ler a documentação fornecida na página inicial, testar os endpoints utilizando o **Hoppscotch** (ou Postman) e criar um documento de mapeamento técnico.

### 📋 Passo a Passo da Atividade:

**1. Pesquisa e Leitura (Análise de Orientação Técnica):**
* Aceda ao site [ReqRes.in](https://reqres.in/).
* Analise a tabela principal da página que contém os *Endpoints* e os métodos disponíveis.
* Descubra qual é a *Base URL* que deverá ser colocada antes de cada caminho.

**2. Teste de Homologação (Mão na Massa):**
Utilizando uma ferramenta de teste de APIs (Hoppscotch.io ou Postman), execute e valide os **3 cenários** abaixo:
* **Cenário A:** Buscar a lista de utilizadores da página 2.
* **Cenário B:** Criar um novo utilizador com o vosso próprio nome e uma profissão (cargo).
* **Cenário C:** Tentar procurar um utilizador que não existe (ex: utilizador com ID 23) e capturar o erro devolvido pela API.

**3. Produção do Entregável:**
Vocês devem documentar o que descobriram. Crie um ficheiro chamado `ANALISE_REQRES_SeuNome.md` (substitua pelo seu nome) e documente os 3 cenários testados seguindo estritamente o modelo de mercado abaixo.

---

# 📡 Documentação de Análise da API - ReqRes

## 1. Cenário A: Listar Utilizadores da Página 2
* **Verbo HTTP:** GET
* **URL Completa:** https://reqres.in/api/users?page=2
* **Body da Requisição:** Nenhum
* **Status Code Esperado:** 200 OK
* **Resposta da API (Exemplo do JSON):**
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

## 2. Cenário B: Criar Novo Utilizador
* **Verbo HTTP:** POST
* **URL Completa:** https://reqres.in/api/users
* **Body da Requisição:** 
{
  "name": "Jonathas",
  "job": "Publicitário Especialista em Growth Marketing"
}
* **Status Code Esperado:** 201 Created
* **Resposta da API (Exemplo do JSON):**
{
  "name": "Jonathas",
  "job": "Publicitário Especialista em Growth Marketing",
  "id": "845",
  "createdAt": "2026-07-03T22:53:30.737Z"
}

## 3. Cenário C: Utilizador Inexistente
* **Verbo HTTP:** GET
* **URL Completa:** https://reqres.in/api/users/23
* **Body da Requisição:** Nenhum
* **Status Code Esperado:** 404 Not Found
* **Resposta da API (Exemplo do JSON):**
{}