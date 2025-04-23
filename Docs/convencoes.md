# 🎓 Sistema Acadêmico - Convenções do Projeto  
Este documento descreve as convenções adotadas no projeto **Sistema Acadêmico**, garantindo organização, padronização e boas práticas de mercado.  

## 📘 Convenções Gerais  

### Estrutura de Código  
- Seguir a arquitetura **MVC modularizada**.  
- Cada módulo deve conter as pastas: `controllers`, `models`, `routes` e `services`.  
- Configurações globais devem ser centralizadas na pasta `config/`.  
- Middleware deve ser armazenado em `middleware/`.  

### Nomeação  
- Seguir o padrão de nomeclatura em PT-BR.
- **Variáveis de Ambiente**: Todas as variáveis devem ser prefixadas com `SA_` (ex.: `SA_DB_HOST`, `SA_API_KEY`).
- **Classes e Models**: PascalCase (ex.: `Aluno`, `Professor`).  
- **Variáveis e Funções**: camelCase (ex.: `criarAtividade`, `turmaId`).  
- **Arquivos**: kebab-case (ex.: `aluno.controller.js`, `frequencia.service.js`).  
- **Migrations e Seeders**: timestamp seguido do nome (ex.: `20250406-create-aluno.js`).  

### Estilo de Código  
- Utilizar **Prettier** para formatação automática.  
- Sempre usar ponto e vírgula (`;`) no final das instruções.  
- Espaçamento de 2 espaços por nível de indentação.  

### Documentação  
- Todo código deve conter comentários claros e objetivos.  
- Rotas devem ser descritas no formato OpenAPI/Swagger.  

---

## 🔐 Convenções de Segurança  
- **Autenticação**: Utilizar JWT para autenticação de usuários.  
- **Senhas**: Sempre armazenar com hash utilizando bcrypt.  
- **Validações**: Todas as entradas devem ser validadas com express-validator.  
- **Permissões**: Implementar RBAC (Role-Based Access Control) para controle de acesso.  

---

## 📂 Estrutura de Pastas  
```plaintext  
src/  
├── modules/  
│   ├── aluno/  
│   │   ├── controllers/  
│   │   ├── models/  
│   │   ├── routes/  
│   │   └── services/  
│   ├── professor/  
│   ├── secretario/  
│   ├── turma/  
│   ├── endereco/  
│   ├── atividade/  
│   ├── entrega/  
│   └── frequencia/  
├── config/  
├── database/  
│   ├── migrations/  
│   └── seeders/  
├── middleware/  
└── index.js  
```  

---

## ✨ Boas Práticas  
- **Clean Code**: Priorizar legibilidade e simplicidade no código.  
- **SOLID**: Aplicar os princípios de design orientado a objetos.  
- **Testes**: Garantir cobertura mínima de 80% com testes unitários e de integração.  
- **Env Variables**: Configurar variáveis de ambiente no arquivo `.env`.  

---

## 🗃️ Convenções de Banco de Dados

### 🧱 Nomenclatura de Tabelas
- Prefixo: `tb_sa_`, singular e descritivo
- Tabelas associativas com nome de ambas as entidades

### 🔑 Chaves
- Primária: `cod_<tabela>` (tipo `CHAR`)
- Estrangeira: `fk_cod_<tabela>_<referência>`
- Ex: `fk_cod_turma_aluno`

### 📊 Padrão de Colunas
```
<tipo>_<nome_campo>_<sigla_tabela>
```

| Prefixo | Tipo SQL         | Exemplo                |
|---------|------------------|------------------------|
| `str`   | VARCHAR / TEXT   | `str_nome_aluno`       |
| `int`   | INTEGER          | `int_idade_aluno`      |
| `dt`    | DATE / TIMESTAMP | `dt_nascimento_aluno`  |
| `bool`  | BOOLEAN          | `bool_ativo_aluno`     |
| `dec`   | DECIMAL          | `dec_nota_final`       |

### 👁️ Views e Procedures
- Views: prefixo `vw_sa_`, para consultas
- Procedures: prefixo `sp_sa_`, camelCase (`sp_sa_ListarAlunos`)
- Funções: `fc_sa_` + camelCase (`fc_sa_CalcularMediaFinal`)

---

## 💻 Convenções de Frontend

### 🔤 Convenções de Código
- Linguagem: React (com Vite ou CRA), preferencialmente TypeScript
- Pastas: `kebab-case`, Componentes: `PascalCase`, Variáveis: `camelCase`
- Usar componentes funcionais com hooks
- Reutilização com subcomponentes

### 🎨 Tailwind CSS
- Estilização rápida e responsiva
- Evitar classes longas (usar `clsx` ou `classnames`)
- Seguir paleta e espaçamentos do Figma

### 📐 Integração com Figma
- Todos os componentes devem ter referência no Figma
- Nome das camadas deve espelhar a estrutura do código
- Checklist por tela: responsividade, fontes, espaçamentos, cores

---

## 📢 Observações Finais  
Este documento deve ser seguido por todos os membros da equipe para garantir consistência e qualidade no desenvolvimento do projeto.

**Este guia é o documento central de referência técnica do Sistema Acadêmico. Todas as equipes (frontend, backend, banco e documentação) devem segui-lo rigorosamente.**