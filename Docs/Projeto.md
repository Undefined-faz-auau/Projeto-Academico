Tabelas

Crie uma sigla de 3 letras que possa expressar o nome da tabela.
Toda tabela deve iniciar com “tb” seguido da sigla do sistema e o nome da tabela: Ex: tb_sia_nome_tabela  Use nomes no singular, nunca plural.
Evite nomes com acrônimos, abreviados ou concatenados.
Para uma tabela associativa (n:n), concatene o nome das duas tabelas envolvidas, ficando a tabela principal na frente. Campos/Colunas
A chave primária deve ter o nome da tabela com o prefixo "cod" quando for do tipo inteiro.
Chaves estrangeiras devem ter o mesmo nome das chaves primárias às quais elas se referem; no caso de autorrelacionamento, segue o mesmo nome e antes da sigla da tabela, deve colocar um descritivo que sinalize a sua função. Ex: cod_fornecedor_matriz_for
Todo nome de campo deve ser composto por 3 caracteres expressando o tipo do campo, concatenado com o nome do campo e com a sigla da tabela de origem. Ex: int_idade_pes (campo de tipo inteiro que armazena a idade na tabela pessoa)
Use nomes no singular, nunca plural.
As siglas dos tipos do campo podem conter variações predefinidas que não afetarão a leitura do desenvolvedor. Conforme tabela abaixo:
image


Views
As “Views” seguem as mesmas regras de Tabelas, mudando apenas o prefixo de “tb” para “vw”
Stored Procedures
As “stored procedures” iniciam com “sp” acompanhado da sigla do sistema, o nome da ação e da tabela envolvida.
As ações que acompanham o nome da “stored procedure” são:
Listar (pode retornar mais de 1 resultado)
Consultar (só pode retornar 1 resultado)
Incluir (terá como ação principal a inserção de 1 registro)
Alterar (terá como ação principal a alteração de 1 registro)
Excluir (terá como ação principal a exclusão de 1 registro)
No nome da “stored procedure” após a sigla do banco, o nome não deve ser separado por “_” (underline) e sim tudo junto com as iniciais em maiúsculo, expressando uma função e sua ação, de forma que fique bastante claro para o desenvolvedor. Ex: sp_sia_ListarNfePorCnpjEmissor
Functions
As “Functions” seguem as mesmas regras da “Stored Procedure”, mudando apenas o prefixo de “sp” para “fc”.



##Conevencoes BackEnd

src/
├── config/            # Configurações de banco de dados, variáveis de ambiente
├── controllers/       # Controladores da aplicação
├── models/            # Modelos de dados
├── routes/            # Rotas da API
├── middlewares/       # Middlewares para autenticação, validação, etc.
├── services/          # Lógica de negócios
├── utils/             # Funções utilitárias
├── validators/        # Validação de entrada de dados
└── server.js          # Ponto de entrada da aplicação
