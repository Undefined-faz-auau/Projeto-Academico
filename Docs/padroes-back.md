# 🚀 Convenções de Backend - Sistema Acadêmico (Node.js + Express)

Este documento estabelece o padrão de arquitetura e organização de código para o backend do **Sistema Acadêmico (sa)**, garantindo legibilidade, separação de responsabilidades, manutenção e expansão do sistema com boas práticas de mercado.

---

## 🔢 Estrutura de Pastas (MVC aprimorado)
```
src/
├── config/         # Configurações globais: conexão DB, variáveis ambiente, JWT
├── controllers/    # Lógica das rotas, conecta services e models
├── models/         # Modelos Sequelize / ORM
├── routes/         # Definição das rotas organizadas por módulo
├── middlewares/    # Middleware para autenticação, erros, logging, etc
├── services/       # Lógica de negócio (sem dependência de framework)
├── utils/          # Funções utilitárias reutilizáveis
├── validators/     # Validações de entrada com Joi, Yup, etc
└── server.js       # Ponto de entrada da aplicação
```

---

## 🔒 Convenções Gerais de Código

### ✅ Padronização
- Linguagem: **JavaScript (ES6+)** ou **TypeScript** (preferencial para projetos maiores)
- Formatação: **Prettier + ESLint** (com regras padronizadas e automação em commit ou CI)

### 🎓 Boas práticas:
- Nomes de arquivos em `kebab-case`
- Variáveis e funções em `camelCase`
- Classes em `PascalCase`
- Nada de `console.log` em produção: use `winston`, `pino`, ou `debug`

---

## 🔗 Controllers
- Cada controller deve ter métodos padronizados: `create`, `update`, `delete`, `getById`, `getAll`
- Controllers devem ser **finos**: sem lógica de negócio

```js
// Exemplo
exports.createAluno = async (req, res) => {
  const aluno = await alunoService.create(req.body);
  return res.status(201).json(aluno);
};
```

---

## 💡 Services
- Lógica de negócio centralizada aqui
- Sem dependência de Express ou req/res
- Podem ser usados por outros services ou controllers

```js
// alunoService.js
const create = async (dados) => {
  // regra: verificar limite da turma antes de cadastrar aluno
};
```

---

## 🔧 Middlewares
- Autenticação JWT
- Validações de permissão (RBAC)
- Tratamento de erros globais
- Logging e rate limiting (se aplicável)

---

## 🔍 Validação
- Validar entradas com bibliotecas como Joi ou Yup
- Toda entrada deve ser validada **antes de atingir o controller**

```js
// middleware
const schema = Joi.object({ nome: Joi.string().required() });
```

---

## 🌐 Versionamento de API
- Use prefixo `/api/v1/` para garantir compatibilidade futura

```http
GET /api/v1/alunos
POST /api/v1/turmas
```

---

## 📊 Logs e Monitoramento
- Use ferramentas como `winston`, `pino`, `log4js`
- Adicione logs para autenticação, erros, e eventos importantes

---

## ⚡ Outros
- Use `.env` para variáveis sensíveis
- Documente a API com Swagger (OpenAPI) ou Postman Collection
- Estruture testes unitários com Jest ou vitest

---

> Este guia deve ser seguido por todos os desenvolvedores do backend para garantir consistência, manutenção e profissionalismo no código.

