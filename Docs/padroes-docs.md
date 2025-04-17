# 🚀 Convenções de Frontend - Sistema Acadêmico (React + Tailwind + Figma)

Este documento define as boas práticas e convenções para o desenvolvimento frontend do **Sistema Acadêmico (sa)**, usando **React**, **Tailwind CSS** e **Figma** como base para design e implementação.

---

## 🔢 Estrutura de Pastas
```
src/
├── assets/         # Imagens, ícones, logos, fontes
├── components/     # Componentes reutilizáveis (ex: Botão, Card, Modal)
├── pages/          # Páginas completas da aplicação (ex: Login, Dashboard)
├── layouts/        # Estrutura base das páginas (ex: Sidebar + Header)
├── services/       # Requisições HTTP (ex: axios)
├── hooks/          # Hooks personalizados (useAuth, useForm, etc.)
├── contexts/       # Context API (ex: AuthContext)
├── styles/         # Configurações do Tailwind, estilos globais
├── router/         # Rotas da aplicação (react-router-dom)
├── types/          # Tipagens e interfaces (se usar TS)
└── App.jsx         # Ponto de entrada da aplicação
```

---

## 🔍 Convenções de Código

### Linguagem:
- React (Vite ou CRA)
- Preferîncialmente com **TypeScript**

### Padrão de escrita:
- Componentes e arquivos em `PascalCase`
- Funções e variáveis em `camelCase`
- Pastas em `kebab-case`

### Componentes:
- Usar **componente funcional** com hooks (sem classe)
- Reutilizar o máximo possível (criar subcomponentes se precisar)
- Incluir prop `children` se for componente de layout

---

## 🌟 Estilização com Tailwind CSS

### Vantagens:
- Rápido, responsivo, baseado em utilitários
- Totalmente personalizável via `tailwind.config.js`

### Boas práticas:
- Evitar strings longas: use classes compostas via `clsx` ou `classnames`
- Preferir **componentes estilizados com props** ao invés de repetir classes
- Cores, fontes e espaçamentos devem seguir o design do Figma

### Exemplo:
```jsx
<button className="px-4 py-2 bg-blue-600 text-white rounded hover:bg-blue-700">
  Entrar
</button>
```

---

## 🎨 Integração com Figma
- Todo componente ou página deve ter referência ao layout correspondente no Figma
- Nome das camadas no Figma deve refletir a estrutura de componentes React
- Designers e devs devem alinhar espaçamentos, cores e responsividade

### Checklist por tela:
- [ ] Mobile e Desktop prontos
- [ ] Fontes e espaçamentos conferidos
- [ ] Componentes reutilizados no Figma e no código
- [ ] Cores do Tailwind mapeadas com a paleta do projeto

---

## 📅 Gerenciamento de Estado
- Usar **Context API** ou **Zustand** para estados globais simples
- Para requisições, usar `axios` com `useEffect` ou **React Query** (se preferir caching)
- Formularios podem usar `react-hook-form`

---

## 📁 Conexão com Backend
- Base URL centralizada no `.env`
- Serviços criados em `src/services/` com `axios.create()`

```js
// services/alunoService.js
export const listarAlunos = () => api.get("/alunos");
```

---

## 📄 Documentação e Contribuição
- Todas as telas/componentes devem ter **comentário explicando props**
- Arquivos principais devem ter docblock `/** ... */`
- Seguir convenções deste documento para novos componentes

---

> Manter este guia atualizado é responsabilidade do time de frontend. Atualizações devem ser discutidas entre os tech leads e validadas em sprint reviews.