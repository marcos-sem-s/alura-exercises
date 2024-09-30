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

##