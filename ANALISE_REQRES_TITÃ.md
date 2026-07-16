# Documentação de Análise da API - ReqRes

## 1. Cenário A: Listar Utilizadores da Página 2
[cite_start]**Verbo HTTP:** GET [cite: 33]
[cite_start]**URL Completa:** https://reqres.in/api/users?page=2 [cite: 34]
[cite_start]**Body da Requisição:** Nenhum [cite: 35]
[cite_start]**Status Code Esperado:** 200 OK [cite: 36]
[cite_start]**Resposta da API (Exemplo do JSON):** [cite: 37]
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
  ],
  "support": {
    "url": "https://reqres.in/#support-heading",
    "text": "To keep ReqRes free, contributions towards server costs are appreciated!"
  }
}

## 2. Cenário B: Criar Novo Utilizador
[cite_start]**Verbo HTTP:** POST [cite: 33]
[cite_start]**URL Completa:** https://reqres.in/api/users [cite: 34]
[cite_start]**Body da Requisição:** [cite: 35]
{
    "name": "[Seu Nome]",
    "job": "Desenvolvedor Full-Stack"
}
[cite_start]**Status Code Esperado:** 201 Created [cite: 36]
[cite_start]**Resposta da API (Exemplo do JSON):** [cite: 37]
{
    "name": "[Seu Nome]",
    "job": "Desenvolvedor Full-Stack",
    "id": "789",
    "createdAt": "2026-07-03T23:09:34.000Z"
}

## 3. Cenário C: Utilizador Inexistente
[cite_start]**Verbo HTTP:** GET [cite: 33]
[cite_start]**URL Completa:** https://reqres.in/api/users/23 [cite: 34]
[cite_start]**Body da Requisição:** Nenhum [cite: 35]
[cite_start]**Status Code Esperado:** 404 Not Found [cite: 36]
[cite_start]**Resposta da API (Exemplo do JSON):** [cite: 37]
{}
lib
<!--
=========================================================
# Quadro Kanban Minimalista 📋
Uma aplicação web simples de "arrastar e soltar" (Drag and Drop) construída para auxiliar no planejamento e organização do desenvolvimento de software.

## 🚀 Tecnologias Utilizadas
* HTML5: Estruturação semântica e atributo nativo `draggable`.
* CSS3: Estilização com Flexbox para as colunas do quadro.
* JavaScript (Vanilla): Lógica de eventos para manipulação do DOM e Drag and Drop API.

## ⚙️ Funcionalidades
* Interface intuitiva dividida em etapas de projeto (A Fazer, Em Andamento, Concluído).
* Movimentação de tarefas entre as colunas em tempo real.
* Feedback visual ao selecionar e arrastar uma tarefa.

## 💻 Como testar
Basta abrir este arquivo no seu navegador.
=========================================================
-->

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quadro Kanban Dev</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f4f5f7;
            color: #172b4d;
            text-align: center;
            margin: 0;
            padding: 20px;
        }
        .board {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }
        .column {
            background-color: #ebecf0;
            width: 300px;
            min-height: 400px;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }
        .column h2 {
            font-size: 16px;
            margin-bottom: 15px;
            text-transform: uppercase;
            color: #5e6c84;
        }
        .task {
            background-color: white;
            margin-bottom: 10px;
            padding: 15px;
            border-radius: 4px;
            cursor: grab;
            box-shadow: 0 1px 2px rgba(0,0,0,0.1);
            transition: transform 0.1s ease;
        }
        .task:active {
            cursor: grabbing;
        }
        .task.dragging {
            opacity: 0.4;
            transform: scale(0.95);
        }
    </style>
</head>
<body>
    <h1>Planejamento de Software</h1>
    <p>Arraste os cards para organizar o andamento do projeto.</p>
    
    <div class="board">
        <div class="column" id="todo">
            <h2>A Fazer</h2>
            <div class="task" draggable="true">Definir escopo do projeto</div>
            <div class="task" draggable="true">Criar repositório no GitHub</div>
        </div>
        
        <div class="column" id="doing">
            <h2>Em Andamento</h2>
            <div class="task" draggable="true">Codificar o Frontend</div>
        </div>
        
        <div class="column" id="done">
            <h2>Concluído</h2>
            <div class="task" draggable="true">Levantamento de requisitos</div>
        </div>
    </div>

    <script>
        const tasks = document.querySelectorAll('.task');
        const columns = document.querySelectorAll('.column');

        // Adiciona eventos aos cards (as tarefas)
        tasks.forEach(task => {
            task.addEventListener('dragstart', () => {
                task.classList.add('dragging');
            });

            task.addEventListener('dragend', () => {
                task.classList.remove('dragging');
            });
        });

        // Adiciona eventos às colunas para receberem os cards
        columns.forEach(column => {
            column.addEventListener('dragover', (e) => {
                e.preventDefault(); // Necessário para permitir o drop
                const draggingTask = document.querySelector('.dragging');
                column.appendChild(draggingTask); // Move o card para a nova coluna
            });
        });
    </script>
</body>
</html>
