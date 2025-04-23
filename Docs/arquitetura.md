# Arquitetura do Projeto - Sistema Acadêmico  

Este documento descreve a arquitetura do projeto **Sistema Acadêmico**, detalhando os principais componentes, tecnologias e estrutura de pastas para auxiliar os desenvolvedores no entendimento e evolução do sistema.  

## 🏗️ Arquitetura Geral  

O projeto segue o padrão **MVC modularizado**, com separação de responsabilidades por entidade. Essa abordagem facilita a escalabilidade, manutenção e aplicação de boas práticas de desenvolvimento, como Clean Architecture.  

### 🔑 Principais Tecnologias  

- **Node.js** + **Express**: Framework backend.  
- **Sequelize ORM**: Gerenciamento do banco de dados relacional (**PostgreSQL**).  
- **JWT**: Autenticação baseada em tokens.  
- **bcrypt**: Hash de senhas.  
- **express-validator**: Validação de dados.  
- **dotenv**: Configuração de variáveis de ambiente.  

### 📂 Estrutura de Pastas  

```plaintext  
src/  
├── modules/  
│   ├── aluno/  
│   │   ├── controllers/  
│   │   ├── models/  
│   │   ├── routes/  
│   │   └── services/  
│   ├── professor/  
│   │   ├── controllers/  
│   │   ├── models/  
│   │   ├── routes/  
│   │   └── services/  
│   ├── secretario/  
│   │   ├── controllers/  
│   │   ├── models/  
│   │   ├── routes/  
│   │   └── services/  
│   ├── turma/  
│   │   ├── controllers/  
│   │   ├── models/  
│   │   ├── routes/  
│   │   └── services/  
│   ├── endereco/  
│   │   ├── controllers/  
│   │   ├── models/  
│   │   ├── routes/  
│   │   └── services/  
│   ├── atividade/  
│   │   ├── controllers/  
│   │   ├── models/  
│   │   ├── routes/  
│   │   └── services/  
│   ├── entrega/  
│   │   ├── controllers/  
│   │   ├── models/  
│   │   ├── routes/  
│   │   └── services/  
│   └── frequencia/  
│       ├── controllers/  
│       ├── models/  
│       ├── routes/  
│       └── services/  
├── config/  
│   └── database.js  
├── database/  
│   ├── migrations/  
│   └── seeders/  
├── middleware/  
│   ├── autenticacao.js  
│   └── autorizacao.js  
└── index.js  
```  

### 📘 Descrição dos Diretórios  

- **modules/**: Contém os módulos principais do sistema, organizados por entidade (aluno, professor, etc.). Cada módulo segue o padrão MVC:  
    - **controllers/**: Lógica de controle das rotas.  
    - **models/**: Definição dos modelos Sequelize.  
    - **routes/**: Definição das rotas específicas do módulo.  
    - **services/**: Regras de negócio e lógica de aplicação.  
- **config/**: Configurações globais, como conexão com o banco de dados.  
- **database/**: Migrations e seeders para gerenciamento do banco de dados.  
- **middleware/**: Middlewares para autenticação e autorização.  
- **index.js**: Ponto de entrada da aplicação.  

### 🔐 Segurança e Autenticação  

- **JWT**: Utilizado para autenticação de usuários.  
- **RBAC (Role-Based Access Control)**: Controle de acesso baseado em papéis (secretário, professor, aluno).  
- **Middlewares**:  
    - `autenticacao.js`: Verifica a validade do token JWT.  
    - `autorizacao.js`: Garante que o usuário tenha permissão para acessar a rota.  

## 🧱 Arquitetura Frontend (React + Tailwind)

### 📁 Estrutura de Pastas Frontend
```
src/
├── assets/         # Imagens, logos, ícones
├── components/     # Componentes reutilizáveis (Botão, Card, etc.)
├── pages/          # Páginas principais (Login, Dashboard, etc.)
├── layouts/        # Estrutura base (Sidebar, Header)
├── services/       # Integração com backend via axios
├── hooks/          # Hooks personalizados
├── contexts/       # Contextos globais (ex: AuthContext)
├── styles/         # Tailwind config e estilos globais
├── router/         # Rotas da aplicação
├── types/          # Tipagens e interfaces (TS)
└── App.jsx         # Ponto inicial da aplicação
```

### 🌐 Estado e Gestão de Dados
- Context API ou Zustand para gerenciamento de estado global
- `axios` + `useEffect` ou React Query para fetch de dados
- `react-hook-form` para gerenciamento de formulários

## 🖥️ Arquitetura Backend Detalhada

### ⚙️ Padrões de Arquitetura
- **Controllers finos**: apenas interface com HTTP, sem lógica de negócio
- **Services**: contêm toda a lógica de domínio isolada
- **Versionamento da API**: `/api/v1/`
- **Validação**: antes dos controllers com Joi/Yup
- **Logging**: `winston` ou `pino` para logs estruturados (não usar console.log em produção)

### 🗂️ Estrutura de Projetos de Documentação
```
docs/
├── README.md
├── regras-de-negocio.md
├── padroes-banco.md
├── backend-convencao.md
├── frontend-convencao.md
├── glossario-e-api.md
└── diagramas/
    ├── casos-de-uso.drawio
    ├── entidade-relacionamento.drawio
    └── classes.drawio
```

## 🧾 Documentação Técnica

### 📋 Documentos Obrigatórios
- **README.md**: Visão geral do sistema
- **regras-de-negocio.md**: Fluxos, permissões e perfis
- **padroes-banco.md**: Modelagem e convenções SQL
- **Documentação da API**: com Swagger ou Postman
- **Diagramas**: Casos de Uso, Entidade-Relacionamento, Classes, Fluxogramas

### ✅ Próximos Passos  

1. Criar models Sequelize com relacionamentos e validações.  
2. Implementar migrations para todas as tabelas.  
3. Desenvolver middlewares de autenticação e RBAC.  
4. Criar seed inicial com um secretário padrão.  
5. Construir controllers e rotas para todas as entidades.  
6. Desenvolver interfaces frontend com React e Tailwind CSS.
7. Implementar testes automatizados com cobertura mínima de 80%.
8. Finalizar documentação técnica e de API.

Essa arquitetura modularizada garante organização, escalabilidade e facilidade de manutenção para o projeto Sistema Acadêmico.