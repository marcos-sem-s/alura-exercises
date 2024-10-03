## Criando um banco
Imagine que você está trabalhando em um sistema para gerenciar uma loja de sucos. Você precisa criar um banco de dados para armazenar as informações sobre os produtos e as vendas da loja.

**Instruções**

- Crie um banco de dados chamado `SUCOS_VENDAS` utilizando o comando CREATE DATABASE.
- Explore as opções de configuração disponíveis no assistente do SSMS para criar um segundo banco de dados chamado `SUCOS_VENDAS_2`. Você pode alterar o tamanho inicial, o aumento automático e o caminho do arquivo do banco de dados.

``` sql
CREATE DATABASE sucos_vendas;
```

2. Com o assistente do SSMS:

    1. Clique com o botão direito na pasta "Bancos de Dados" e selecione "Novo Banco de Dados...".
    2. Digite o nome do banco de dados no campo "Nome".
    3. Configure as opções de tamanho inicial, aumento automático e caminho do arquivo do banco de dados.
    4. Clique em "OK" para criar o banco de dados.
    5. Você pode ver o banco de dados criado na pasta "Bancos de Dados" no SSMS.

Lembre-se que você pode usar o botão "Script" para ver o código SQL gerado pelo assistente.

<br>

## Excluindo um banco
Imagine que você é o administrador de um sistema de vendas de uma empresa de sucos. Você criou duas bases de dados: `SUCOS_VENDAS` e `SUCOS_VENDAS_2`. Mas, a empresa decidiu usar apenas a `SUCOS_VENDAS`.

**Instruções**

Como você faria para excluir a base de dados `SUCOS_VENDAS_2` usando o SQL Server Management Studio (SSMS)?

Lembre-se de verificar se o proprietário da base de dados é o login `sa` para garantir que você tenha permissão para excluir.

Depois de excluir a base de dados, como você pode verificar se a exclusão foi realizada com sucesso?

Dica: Use o comando `DROP DATABASE` e explore as opções do SSMS para verificar a exclusão.

``` sql
DROP DATABASE suco_vendas_2;
```

<br>

## Banco de Dados
Anna Júlia começou seus estudos em SQL Server e para isso criou duas bases de dados, Empresa1 e Empresa2, sem popular com tabelas e informações. Mediante a análise dessas informações, quais comandos abaixo foram executados com sucesso pela Anna Júlia?

- [ ] Os comandos: `CREATE DATABASE [Empresa1];` e `DELETE [Empresa1];` permitiram criar a base de dados chamada Empresa1 e excluí-la subsequentemente.
- [ ] O comando `DROP [Empresa2]` pode ser executado logo após o `CREATE DATABASE [Empresa2];` se a intenção for deletar a base de dados Empresa2.
- [x] Executando `CREATE DATABASE [Empresa1];` e `CREATE DATABASE [Empresa2];` serão criadas duas bases de dados, a Empresa1 e a Empresa2.
- [ ] Rodar o comando `NEW DATABASE [Empresa1];` constrói uma nova base de dados chamada Empresa1 pronta para se populada de tabelas.

<br>

## Criando tabelas
Crie a tabela [TABELA DE CLIENTES] com os seguintes campos:

- [CPF]: tipo CHAR com tamanho 11.
- [NOME]: tipo VARCHAR com tamanho 150.
- [RUA]: tipo VARCHAR com tamanho 150.
- [COMPLEMENTO]: tipo VARCHAR com tamanho 150.
- [BAIRRO]: tipo VARCHAR com tamanho 150.
- [ESTADO]: tipo CHAR com tamanho 2.
- [CEP]: tipo CHAR com tamanho 8.
- [DATA DE NASCIMENTO]: tipo DATE.
- [IDADE]: tipo SMALLINT.
- [SEXO]: tipo CHAR com tamanho 1.
- [LIMITE DE CREDITO]: tipo MONEY.
- [VOLUME MINIMO]: tipo FLOAT.
- [PRIMEIRA COMPRA]: tipo BIT.

Lembre-se de usar os colchetes ([]) para os nomes dos campos e da tabela (ou não), e de separar os campos por vírgula.

``` sql
CREATE TABLE clientes (
	cpf CHAR(11),
	nome VARCHAR(150),
	rua VARCHAR(150),
	complemento VARCHAR(150),
	bairro VARCHAR(150),
	estado CHAR(2),
	cep CHAR(8),
	data_nascimnto DATE,
	idade SMALLINT,
	sexo CHAR(1),
	limite_credito MONEY,
	volume_minimo FLOAT,
	primeira_compra BIT
);
```

<br>

## Criando a tabela de produtos
Crie uma tabela chamada `PRODUTOS` com as seguintes colunas:

- Código do produto: Um código único para cada produto, com no máximo 10 caracteres.
- Nome do produto: O nome completo do produto, com no máximo 50 caracteres.
- Descrição: Uma descrição detalhada do produto, com no máximo 200 caracteres.
- Preço: O preço do produto, com duas casas decimais.
- Estoque: A quantidade de produtos em estoque.
- Categoria: A categoria do produto, com no máximo 20 caracteres.

Lembre-se de definir a coluna `Código do produto` como chave primária e garantir que ela não pode ser nula.

``` sql
CREATE TABLE produtos (
	codigo_produto VARCHAR(20) NOT NULL PRIMARY KEY, 
	nome_produto VARCHAR(50), 
	embalagem VARCHAR(50), 
	tamanho VARCHAR(50), 
	sabor VARCHAR(50), 
	preco_lista SMALLMONEY
);
```

<br>

## Alterando tabelas
Pensando mais a fundo nas tabelas da nossa empresa, a equipe responsável pela modelagem nos informou que o CPF também é uma chave primária, porém, da tabela de clientes.

Como já criamos essa tabela de clientes em etapas anteriores, surge a questão: 

``` sql
ALTER TABLE clientes
ALTER COLUMN cpf CHAR(11) NOT NULL;

ALTER TABLE clientes
ADD CONSTRAINT pk_clientes PRIMARY KEY CLUSTERED(cpf);
```

<br>

## Desafio: Tabela vendedores
Nosso banco de dados precisa de mais uma tabela. Para realizar essa demanda, fomos informados sobre a necessidade de considerar alguns critérios pré-selecionados por uma solicitante. Nesse sentido, segue abaixo as informações que precisamos ter em mente ao realizar esse desafio:

- O nome da tabela deve ser TABELA DE VENDEDORES.
- Vendedor tem como chave o número interno da matrícula (Nome do campo MATRICULA) que deve ser um texto de 5 posições.
- O nome do vendedor (Nome do campo NOME) deve ser um texto de 100 posições.
- % de comissão. Este campo (Nome do campo PERCENTUAL COMISSÃO) representa o percentual de comissão garantida pelo vendedor sobre cada venda.
- Diante dessa demanda, qual comando podemos utilizar para a criação desta tabela?

``` sql
CREATE TABLE vendedores (
	matricula CHAR(5),
	nome VARCHAR(100),
	porcentagem_comissao FLOAT
)
```
