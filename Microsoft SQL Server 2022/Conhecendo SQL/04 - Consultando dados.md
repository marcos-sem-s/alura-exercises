## Todos os dados
Escreva o comando SQL para visualizar todos os dados da tabela `[TABELA DE CLIENTES]`.

``` sql
SELECT * 
FROM clientes;
```

<br>

## Colunas específicas
1. Selecione somente as colunas `estado` e `nome`.

``` sql
SELECT estado, nome
FROM clientes;
```

2. Ordene por `nome`.

``` sql
SELECT estado, nome
FROM clientes
ORDER BY nome;
```

<br>

## Selecionando informações
Bianca é cientista de dados em uma empresa de consultoria e precisa de uma lista com o nome dos projetos (NOME) cadastrados na tabela TB PROJECT para repassar para a liderança. Quais comandos em SQL Bianca pode usar para retirar essa informação?

**Selecione 2 alternativas**

- [x] `SELECT [NOME] FROM [TB PROJECT];`

- [ ] `SELECT * FROM [TB PROJECT];`

- [x] `SELECT NOME AS ‘NOME DOS PROJETOS’ FROM [TB PROJECT]`

- [ ] `SELECT ALL FROM [TB PROJECT];`

<br>

## Apelidando colunas
Nossa demanda é a seguinte: precisamos de uma tabela que contenha o nome, o CPF e a cidade de nossos clientes. Essa tabela será enviada para outra área da nossa empresa, portanto, ela precisa ser bem descritiva.

Selecione as coluna `nome` como `nome_cliente`, `estado` como `UF` e `cpf`.

``` sql
SELECT nome AS nome_cliente, estado AS uf, cpf
FROM clientes;
```

<br>

## Desafio: quem são as pessoas vendedoras?
Seguindo nos desafios da tabela das pessoas vendedoras, anteriormente criamos e preenchemos com informações, agora o desafio é visualizar a tabela `[TABELA DE VENDEDORES]`. O objetivo é mostrar o campo `MATRICULA` com o apelido `IDENTIFICADOR` e o campo `NOME` apelidado por `NOME DO VENDEDOR`.

``` sql
SELECT matricula as identificador, nome as nome_vendedor
FROM vendedores;
```

<br>

## Seleção distinta
Como identificar quais sabores diferentes de suco a Frutally vende?

``` sql
SELECT DISTINCT nome
FROM produtos;
```

<br>

## Eliminando duplicatas
Na empresa da Carol alguns processos estão sendo migrados de planilhas para o banco de dados utilizando SQL. A tabela de histórico de vendas foi criada utilizando o SQL Server e já foi preenchida com o histórico de vendas da empresa. No entanto, Carol estava acostumada a remover linhas duplicadas nas planilhas para identificar o nome dos vendedores que realizaram pelo menos uma venda. Como ela pode eliminar os vendedores duplicados da tabela TB_VENDA usando a linguagem SQL?

**Selecione 2 alternativas**

- [x] 
``` sql
SELECT DISTINCT ID_VENDEDORES
FROM TB_VENDA 
ORDER BY ID_VENDEDORES;
```

- [x]
``` sql
SELECT DISTINCT ID_VENDEDORES
FROM TB_VENDA
```

- [ ]
``` sql
SELECT ID_VENDEDORES
FROM TB_VENDA 
ORDER BY ID_VENDEDORES
```

- [ ]
``` sql
SELECT * 
FROM TB_VENDA
```
