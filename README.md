# Criando Aplicativos Sem Codigo
Criação de aplicativos desktop usando o LibreOffice Base

## Com o MariaDB

Idêntico ao que se fazia (ainda se faz?) com o MS Access. Acredito que a internet desbancou todas as ferrametnas desktop, mas não precisa ser assim. 

Para mim, para você, para um projeto pequeno ele é funcional e muito amigável para quem usa. Tem mais, tá usando MySQL através do JDBE e pode usar praticamente qualquer SGBD.

Bem, pelo menos serviu para eu matar a saudade da primeira ferramenta que me permitiu criar um aplicativo "profissional". Eu cheguei a criar controle de estoque no Access. Me empolguei tanto que criei um site chamado "Cantinho dos Amantes do Access" em 1999:

https://ribafs.me/access/

## URL deste projeto

https://github.com/ribafs/aplicativos-sem-codigo

## Tutorial

Publiquei um tutorial bem detalhado sobre como configurei o LibreOffice Base e como criei um aplicativo para cadastro de clientes e pedidos (relacionados) e com form master-details. Confira:

https://ribafs.medium.com/criando-aplicativos-sem-c%C3%B3digo-6a9cc69301f6

## Material extra
Alguns tutoriais que encontrei e também o aplicativo criado para este repositório e o tutorial [CadastroLibreBase.odb](CadastroLibreBase.odb).

## Usando o PostgreSQL

[PostgreSQL](PostgreSQL.md)

Veja também as capturas na pasta img

[imagens](img)

## Criando aplicativo com LibreOffice Base

Algo parecido com o que eu fazia com o MS Access

Existe também como "descer" e usuar código, como fazia com o VBA no Access (nem sei se ainda se faz)

Documentação (guias, inclusive em pt)

- https://documentation.libreoffice.org/en/english-documentation/
- https://documentation.libreoffice.org/assets/Uploads/Documentation/pt-br/OutrosDocs/Introducao-ao-Base.pdf
- https://help.libreoffice.org/latest/pt-BR/text/shared/explorer/database/dabawiz00.html?&DbPAR=BASE&System=UNIX

Temos uma IDE (Integrated Development Environment) para ajudar a criar macros em Basic.

Ferramentas - Opções - LibreOffice - IDE do Basic

Marque as opções desejadas

Veja

https://help.libreoffice.org/latest/pt-BR/text/shared/optionen/BasicIDE.html?DbPAR=SHARED#bm_id4077578

Criar macros

https://help.libreoffice.org/latest/pt-BR/text/sbasic/shared/01/06130000.html?DbPAR=BASIC#bm_id3145786


## Configurando o LibreOffice Base para o MariaDb

Usando o JDBC

Irei demonstrar a criação de um pequeno cadastro de clientes e pedidos, estando estas duas tabelas relacionadas para que possamos usar o recurso de master-details do LibreOffice Base

## Baixar o JRE de

https://www.java.com/pt-BR/download/manual.jsp

Descompacte e copie para uma pasta que desejar

https://downloads.mariadb.com/Connectors/java/

Baixar o último estável, que hoje é o connector-java-2.7.3/

Salvar e Manter numa pasta

## Abrir LibreOffice

Ferramentas - Opções - LibreOffice - Avançado - Adicionar

Selecione a pasta do JRE - OK

Então clique em Caminho da Classe

- Adicionar Arquivo
- Adicionar Arquivo
- Indicar o mariadb.jar baixado

OK

Reiniciar agora

Criando o Aplicativo

Arquivo - Novo - Banco de Dados

Cria antes um banco no MySQL e importe para ele o script para o qual deseja criar o sistema no LibreOffice Base

No repositório abaixo encontrará o script db.sql que usei neste exemplo:

https://github.com/ribafs/aplicativos-sem-codigo

Abaixo em

Conectar a um banco de dados existente - MySQL

Próximo

Conectar utilizando JDBC

Próximo

Nome do banco de dados - cadastro

Servidor - localhost

Número da porta - 3306

Testar classe -

Próximo

Nome de usuário - root

Caso use senha no MySQL marque Senha obrigatória

Finalizar

Nome - entre o nome do sistema que será criado no LibreOffice Base, que poderá conter tabelas, consultas, formulários e relatórios

Clique em Tabelas e veja que as tabelas do seu banco aparecem. Caso não queira trabalhar com alguma, clique nela com o botão direito - Excluir

Clique em Formulários

Duplo clique em Assistente de formulários

Clique em >> para adicionar todos os campos da tabela Clientes (acima)

Próximo

Opção para adicionar subformulários (no caso de tabelas relacionadas)

Adicionar subformulário
- Subformulário baseado em relação existente
- Selecionar cadastro.pedidos (caso o seu banco chame-se cadastro)

Próximo

Selecione todos os campos clicando em >>

Próximo

Escolha o leyout. Eu gosto do primeiro (Colunas - Rótulos à esquerda) para o form principal e manenho para o sub Como planilha (ou o último)

Próximo

O formulário deve exibir todos os dados

Próximo

Estilo

Selecione e Próximo

Nome do formulário - frmClientesPedidos

Concluir

Repositório com o SQL para o MariaDb que usei no aplicativo citado. Também encontrará o próprio aplicativo que criei para este tutorial, portanto se tiver o LibreOffice basta abrir que verá o aplicativo, com o form master-details, um relatório de clientes. Explore e compartilhe comigo pois comecei a descobrir hoje.

# Licença

MIT
