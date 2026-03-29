# 📚 Sistema de Gerenciamento de Biblioteca

Projeto desenvolvido como desafio prático da **Fase 1** da pós-graduação em **Desenvolvimento Full Stack** da **FIAP PósTech**.

---

## 🎯 Sobre o Projeto

API REST para gerenciamento de uma biblioteca, com funcionalidades completas de CRUD para **Livros** e **Editoras**. O projeto foi desenvolvido com foco em boas práticas de desenvolvimento, tipagem estática e integração com banco de dados em nuvem.

---

## 🚀 Tecnologias Utilizadas

- **TypeScript 5** — tipagem estática e código mais seguro
- **Node.js** — ambiente de execução
- **Express** — framework para criação da API REST
- **Prisma ORM** — comunicação com o banco de dados e migrations
- **PostgreSQL** — banco de dados relacional
- **Supabase** — plataforma de banco de dados em nuvem (gratuita)
- **Zod** — validação de dados nas requisições

---

## 📁 Estrutura do Projeto
```
biblioteca-api/
├── prisma/
│   └── schema.prisma
├── src/
│   ├── controllers/
│   ├── services/
│   ├── routes/
│   ├── middlewares/
│   └── server.ts
├── .env.example
├── package.json
└── tsconfig.json
```

---

## 🗄️ Entidades

### Livro
| Campo | Tipo | Descrição |
|-------|------|-----------|
| id | UUID | Identificador único gerado automaticamente |
| titulo | String | Título do livro |
| autor | String | Nome do autor |
| isbn | String | ISBN único do livro |
| anoPublicacao | Int | Ano de publicação |
| editoraId | UUID | Relacionamento com Editora (opcional) |

### Editora
| Campo | Tipo | Descrição |
|-------|------|-----------|
| id | UUID | Identificador único gerado automaticamente |
| nome | String | Nome da editora |
| pais | String | País de origem (opcional) |

---

## 🔗 Endpoints da API

### Livros
| Método | Rota | Descrição |
|--------|------|-----------|
| GET | `/livros` | Lista todos os livros |
| GET | `/livros/:id` | Busca livro por ID |
| POST | `/livros` | Cadastra novo livro |
| PUT | `/livros/:id` | Atualiza livro |
| DELETE | `/livros/:id` | Remove livro |

### Editoras
| Método | Rota | Descrição |
|--------|------|-----------|
| GET | `/editoras` | Lista todas as editoras |
| GET | `/editoras/:id` | Busca editora por ID |
| POST | `/editoras` | Cadastra nova editora |
| PUT | `/editoras/:id` | Atualiza editora |
| DELETE | `/editoras/:id` | Remove editora |

---

## ⚙️ Como Rodar o Projeto

### Pré-requisitos
- Node.js instalado
- Conta no [Supabase](https://supabase.com) (gratuita)

### Passo a passo
```bash
# 1. Clone o repositório
git clone https://github.com/adriana011726/biblioteca-api.git
cd biblioteca-api

# 2. Instale as dependências
npm install

# 3. Configure as variáveis de ambiente
cp .env.example .env
# Edite o .env com a URL do seu banco no Supabase

# 4. Crie as tabelas no banco
npx prisma migrate dev

# 5. Rode o projeto
npm run dev
```

A API estará disponível em `http://localhost:3000`

---

## 📝 Exemplo de Uso

**Cadastrar um livro:**
```json
POST /livros
{
  "titulo": "Tratados das ENÉADAS",
  "autor": "PLOTINO",
  "isbn": "9780132350884",
  "anoPublicacao": 2025
}
```

---

## 💡 O que Aprendi

- Como estruturar uma API REST com **arquitetura em camadas** (routes → controllers → services)
- Uso do **TypeScript** para garantir tipagem e segurança no código
- Como usar o **Prisma ORM** para modelar entidades, criar relacionamentos e rodar migrations
- Integração com banco de dados **PostgreSQL** em nuvem usando o **Supabase**
- Validação de dados com **Zod** para retornar erros claros ao front-end
- Boas práticas como uso de variáveis de ambiente e tratamento global de erros

---

## 👩‍💻 Autora

Desenvolvido por **Adriana** durante a Pós-graduação em Desenvolvimento Full Stack — FIAP PósTech.
