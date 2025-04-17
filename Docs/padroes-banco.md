# 📂 Convenções de Banco de Dados - Sistema Acadêmico (sigla: **sa**)

Este documento define os padrões adotados na modelagem e implementação do banco de dados do Sistema Acadêmico (**sa**), alinhando-se com boas práticas de mercado para garantir legibilidade, manutenção e consistência entre equipes.

---

## 📅 1. Nomenclatura de Tabelas

- Toda tabela deve ter prefixo: `tb_sa_`
- Usar **nomes descritivos no singular**
- Evitar siglas pouco intuitivas, acrônimos ou abreviações

### Exemplo:
- `tb_sa_aluno`
- `tb_sa_turma`
- `tb_sa_disciplina`
- `tb_sa_matricula` 

### Tabelas associativas (N:N):
- `tb_sa_aluno_turma` (ordem: entidade principal primeiro)

---

## 🔢 2. Campos/Colunas

### ⚡ Chave Primária:
- Nome: `cod_<nome_tabela>`
- Tipo: `CHAR`

**Exemplo:**
- `cod_aluno`
- `cod_turma`

### ⛓ Chaves Estrangeiras:
- Devem seguir o nome da chave primária referenciada

**Exemplo:**
- `fk_cod_turma_tabela` (referencia turma de origem)
- `fk_cod_turma_aluno` (em caso onde a tabela aluno recebe como foreign key o código da turma.)

### 🔄 Padrão de nomes para colunas:
```
<tipo>_<nome_campo>_<sigla_tabela>
```

### Tipos e Prefixos Recomendados:
| Prefixo | Tipo SQL Sugerido | Uso                           |
|---------|-------------------|--------------------------------|
| int     | INTEGER           | Idades, códigos, números simples |
| str     | VARCHAR / TEXT    | Nomes, textos curtos            |
| dt      | DATE / TIMESTAMP  | Datas                          |
| bool    | BOOLEAN           | Campos de verdadeiro/falso     |
| dec     | DECIMAL           | Notas, faltas                  |

### Exemplo:
- `str_nome_aluno`
- `int_numero_turma`
- `bool_ativo_aluno`

---

## 📖 3. Views
- Prefixo: `vw_sa_`
- Seguem mesmo padrão das tabelas
- Utilizadas para consultas complexas ou agrupamentos recorrentes

**Exemplo:**
- `vw_sa_aluno_turma_ativa`

---

## 🔧 4. Stored Procedures
- Prefixo: `sp_sa_`
- Nome da ação + entidade, em camelCase
- Ações permitidas: `Listar`, `Consultar`, `Incluir`, `Alterar`, `Excluir`

**Exemplo:**
- `sp_sa_ListarAlunosPorTurma`
- `sp_sa_IncluirAluno`

---

## 🔢 5. Funções (Functions)
- Prefixo: `fc_sa_`
- Mesmo padrão das stored procedures

**Exemplo:**
- `fc_sa_CalcularMediaFinal`

---

## 🔹 6. Regras de Negócio: Turmas e Matrículas

### Formato da Matrícula
- Matrícula gerada automaticamente:
  - Padrão: `T<numero_turma><numero_ordem>`
  - Exemplo: `T1150040` = turma 115, aluno 40

### Controle de Capacidade da Turma
- Cada turma possuirá um campo: `int_capacidade_turma`
- Antes de inserir uma matrícula:
  - Verificar se o número de alunos atuais < capacidade
  - Caso contrário, retornar aviso: "Turma cheia. Deseja tentar outra?"

---

## 💡 Observações finais
- Evite hardcodes ou regras na aplicação que não estejam documentadas
- Garanta que nomes e padrões sejam respeitados por todas as equipes
- Tech Lead: Atualize este documento sempre que novas entidades forem criadas ou modificadas

