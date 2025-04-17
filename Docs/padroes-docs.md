# 📃 Convenções de Documentação - Sistema Acadêmico (sa)

Este guia define o padrão e a estrutura da documentação oficial do projeto **Sistema Acadêmico (sa)**, com o objetivo de manter consistência, clareza e rastreabilidade entre os membros das equipes (frontend, backend, banco de dados e design).

---

## 🔢 Estrutura da Pasta `docs/`
```
docs/
├── README.md                   # Visão geral do sistema
├── regras-de-negocio.md       # Perfis, permissões, fluxos
├── padroes-banco.md           # Convenção de modelagem de dados
├── backend-convencao.md       # Estrutura e padrões de backend
├── frontend-convencao.md      # Estrutura e padrões de frontend
├── diagramas/
│   ├── casos-de-uso.drawio
│   ├── entidade-relacionamento.drawio
│   ├── classes.drawio
│   └── fluxograma-operacional.drawio
└── glossario-e-api.md         # Termos técnicos e estrutura de endpoints
```

---

## 📕 Documentos obrigatórios

| Arquivo                    | Responsáveis                 | Objetivo                                               |
|---------------------------|-------------------------------|--------------------------------------------------------|
| `README.md`               | Scrum Master + Tech Leads     | Apresenta objetivos, stack, estrutura geral            |
| `regras-de-negocio.md`    | PO + Documentação            | Define papeis, regras de fluxo, políticas de acesso   |
| `padroes-banco.md`        | Banco de Dados                | Padrões de nomeação, chaves, tipos, procedures        |
| `backend-convencao.md`    | Tech Lead Backend             | Estrutura do projeto, uso de services e autenticação |
| `frontend-convencao.md`   | Tech Lead Frontend            | Estrutura, padrões de componentes e integração com Figma |
| `glossario-e-api.md`      | Documentação + Backend        | Descrição de endpoints e termos padronizados         |

---

## 📈 Diagramação visual

Os diagramas devem ser organizados na pasta `docs/diagramas/` e podem ser elaborados com **Draw.io**, **Figma**, ou **Lucidchart**, seguindo as boas práticas de modelagem UML.

### Diagramas obrigatórios:
- Casos de Uso (baseado nas interações de cada perfil)
- Diagrama ER (relacionamentos do banco de dados)
- Diagrama de Classes (baseado nos models do backend)
- Fluxograma de Ações (ex: fluxo de entrega de atividade)

---

## ✏️ Padrão de escrita Markdown
- Utilize `#`, `##`, `###` para títulos hierárquicos
- Use listas ordenadas (`1.`) para sequências e não ordenadas (`-`) para tópicos
- Coloque blocos de código com crase tripla `` ``` ``
- Utilize tabelas sempre que for listar elementos relacionados

---

## 🎓 Recomendações Gerais
- Toda mudança relevante na documentação deve ser registrada em commit separado com mensagem `docs: atualização em <arquivo>`
- Evite arquivos duplicados ou desatualizados
- Sempre vincule arquivos `.md` com os `.drawio` correspondentes nos diagramas

---

> A equipe de documentação é responsável por manter este guia e revisar a organização de `docs/` em toda sprint review.

