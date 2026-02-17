<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=24&height=120&section=header"/>

<h1 align="center">📋 Kanban Board</h1>

<p align="center">
  Quadro de tarefas com front-end interativo e back-end com API REST e banco de dados MySQL.
</p>

<div align="center">

  [![Demo](https://img.shields.io/badge/🌐%20Acessar%20Projeto-2482FF?style=for-the-badge)](https://https-shini.github.io/quadro-de-tarefas/)
  [![Código](https://img.shields.io/badge/Ver%20Código-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/https-shini/quadro-de-tarefas)

</div>

---

## 📌 O que é este projeto?

O **Kanban Board** é um quadro visual para organizar tarefas. O projeto é dividido em duas partes:

- **Front-end** — a interface que o usuário vê e usa no navegador
- **Back-end** — o servidor que salva, busca e atualiza as tarefas no banco de dados

As tarefas são organizadas em 4 colunas:

| Coluna | Significado |
|---|---|
| **TO DO** | Tarefas que ainda não começaram |
| **IN PROGRESS** | Tarefas em andamento |
| **TO REVIEW** | Tarefas prontas, aguardando revisão |
| **DONE** | Tarefas concluídas ✅ |

---

## 🛠️ Tecnologias utilizadas

**Front-end**
- HTML, CSS e JavaScript puro

**Back-end**
- Node.js + Express — servidor e rotas da API
- MySQL — banco de dados para salvar as tarefas
- mysql2 — conexão do Node.js com o MySQL
- dotenv — variáveis de ambiente (configurações sensíveis)
- cors — permite que o front-end acesse a API

---

## 🗂️ Estrutura de arquivos

```
quadro-de-tarefas/
│
├── front-end/
│   ├── index.html         → Página principal
│   ├── style.css          → Visual e layout
│   └── script.js          → Interatividade (arrastar, criar cards)
│
└── back-end/
    ├── server.js          → Inicia o servidor
    ├── app.js             → Configura o Express
    ├── router.js          → Define as rotas da API
    ├── controllers/
    │   └── tasksController.js   → Recebe as requisições e responde
    ├── middlewares/
    │   └── tasksMiddleware.js   → Valida os dados antes de salvar
    └── models/
        ├── connection.js        → Conecta ao banco de dados
        └── tasksModel.js        → Consultas SQL (buscar, criar, editar, deletar)
```

---

## 🌐 API — Endpoints disponíveis

A API permite realizar 4 operações com as tarefas:

| Método | Rota | O que faz |
|---|---|---|
| `GET` | `/tasks` | Retorna todas as tarefas |
| `POST` | `/tasks` | Cria uma nova tarefa |
| `PUT` | `/tasks/:id` | Atualiza título e status de uma tarefa |
| `DELETE` | `/tasks/:id` | Remove uma tarefa |

### Exemplos de uso

**Criar uma tarefa** — envie um JSON com o título:
```json
POST /tasks
{
  "title": "Estudar Node.js"
}
```

**Atualizar uma tarefa** — envie o novo título e o novo status:
```json
PUT /tasks/1
{
  "title": "Estudar Node.js",
  "status": "concluído"
}
```

**Resposta ao criar** — a API devolve o ID da tarefa criada:
```json
{ "insertId": 7 }
```

---

## ✅ Validações

Antes de salvar qualquer dado, a API verifica:

- O campo `title` é **obrigatório** em criações e atualizações
- O campo `status` é **obrigatório** em atualizações
- Se algum campo estiver faltando ou vazio, a API responde com erro `400` e uma mensagem explicando o problema

---

## 🚀 Como rodar o projeto localmente

### Pré-requisitos

Você vai precisar ter instalado na sua máquina:
- [Node.js](https://nodejs.org)
- [MySQL](https://www.mysql.com)

### Passo a passo

**1. Clone o repositório**
```bash
git clone https://github.com/https-shini/quadro-de-tarefas.git
cd quadro-de-tarefas
```

**2. Instale as dependências do back-end**
```bash
cd back-end
npm install
```

**3. Configure as variáveis de ambiente**

Crie um arquivo `.env` dentro da pasta `back-end` com os seus dados do MySQL:
```
MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=sua_senha
MYSQL_DB=kanban
PORT=3333
```

**4. Crie o banco de dados**

No MySQL, execute:
```sql
CREATE DATABASE kanban;

USE kanban;

CREATE TABLE tasks (
  id INT AUTO_INCREMENT PRIMARY KEY,
  title VARCHAR(255) NOT NULL,
  status VARCHAR(100) NOT NULL,
  created_at VARCHAR(100) NOT NULL
);
```

**5. Inicie o servidor**
```bash
npm start
```

O servidor estará rodando em `http://localhost:3333` 🎉

**6. Abra o front-end**

Abra o arquivo `index.html` no navegador. Certifique-se de que o endereço da API no `script.js` aponta para `http://localhost:3333`.

---

## 🌐 Experimente agora

Não quer rodar localmente? Acesse a versão online:

👉 **[https://https-shini.github.io/quadro-de-tarefas/](https://https-shini.github.io/quadro-de-tarefas/)**

---

<div align="center">

Feito com 💙 — sinta-se à vontade para usar e melhorar!

⭐ Se gostou, deixe uma estrela no repositório!

</div>

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=24&height=120&section=footer"/>
