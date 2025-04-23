# Git Flow do Projeto 🎓 Sistema Acadêmico  

## 🧠 Convenções de Desenvolvimento  

### Commits  
- Seguir o padrão **Conventional Commits**:  
    - `feat(aluno)`: Adição de nova funcionalidade.  
    - `fix`: Correção de bugs.  
    - `docs`: Alterações na documentação.  
    - `style`: Alterações de estilo (espaços, formatação).  
    - `refactor`: Refatoração de código.  
    - `test`: Adição ou modificação de testes.

### Branches  
- Padrão de nomenclatura:  
    - `main`: Branch principal.  
    - `develop`: Branch de desenvolvimento.
    - `feature/nome-da-feature`: Para novas funcionalidades.  
    - `bugfix/nome-do-bug`: Para correções de bugs.  
    - `hotfix/nome-do-hotfix`: Para correções urgentes.  

### Pull Requests  
- Todo PR deve ser revisado por pelo menos 1 desenvolvedor.  
- Descrever claramente o objetivo e as alterações realizadas.  
- Garantir que todos os testes passem antes de solicitar o merge.  

## 🚀 Fluxo de Trabalho  

1. **Criação de Branch**  
   - Sempre criar uma branch a partir da `develop`.  
   - Nomear a branch seguindo o padrão de nomenclatura.  

2. **Desenvolvimento**  
   - Realizar commits pequenos e frequentes.  
   - Garantir que o código segue os padrões do projeto.
   - Commits devem ser claros e seguir o padrão Conventional Commits.

3. **Testes**  
   - Executar todos os testes antes de abrir um PR.  
   - Garantir que novas funcionalidades possuem cobertura de testes.  

4. **Pull Request**  
   - Abrir um PR para a branch `develop`.  
   - Adicionar revisores e descrever as alterações realizadas.
   - Incluir screenshots para mudanças visuais.
   - Referenciar a issue relacionada (se existir).

5. **Revisão e Merge**  
   - Revisores devem verificar o código e sugerir melhorias, se necessário.  
   - Após aprovação, realizar o merge na branch `develop`.  

6. **Deploy**  
   - O deploy será realizado a partir da branch `main`.  
   - Releases devem ser tagueadas seguindo SemVer (v1.0.0, v1.0.1).

## 🌟 Boas Práticas  

- Manter o código limpo e bem documentado.  
- Seguir os princípios de Clean Code e Clean Architecture.  
- Garantir que todas as alterações estão alinhadas com as regras de negócio do sistema.
- Nunca fazer push direto para `main` ou `develop`.
- Rebase em vez de merge quando estiver atualizando sua branch de feature.
- Resolver conflitos na sua branch, não na `develop`.

## 📋 Validação em Revisões

- **Padronização é prioridade**: verificar se as convenções estão sendo seguidas.
- **Atualização contínua**: documentos e código devem evoluir juntos.
- **Validação em sprint review**: qualquer mudança deve ser discutida.
- **Sem hardcodes não documentados**: todo código deve seguir as convenções.

## 📘 Documentação no Git

- Manter o README.md do projeto sempre atualizado.
- Commits de documentação devem usar o prefixo `docs:`.
- Alterações importantes devem ser documentadas no CHANGELOG.md.
- Ao modificar documentação: `docs: atualização em <arquivo>`.

Este fluxo de trabalho visa garantir qualidade, rastreabilidade e organização no desenvolvimento do projeto Sistema Acadêmico.