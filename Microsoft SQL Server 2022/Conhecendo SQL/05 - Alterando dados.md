## Filtros no SQL
Ainda sobre a personalização das consultas, lembre-se que nos passos anteriores criamos uma consulta que exibe o nome, CPF e estado de cada um dos clientes. Supondo que quiséssemos apenas os clientes que realizaram a primeira compra para direcionar uma campanha de marketing para esse público específico, como poderíamos construir essa consulta?

``` sql
SELECT nome AS nome_cliente, estado AS uf, primeira_compra
FROM clientes
WHERE primeira_compra = 1;
```

<br>

## Filtros em vários tipos
Para te ajudar a consolidar o aprendizado sobre operadores comparativos e funções de data, pense em como você usaria esses recursos para responder às seguintes perguntas:

1. Quais produtos custam menos de R$ 10,00?

``` sql
SELECT *
FROM produtos
WHERE preco < 10;
```

2. Quais clientes nasceram no mês de julho?

``` sql
SELECT DISTINCT(nome)
FROM clientes
WHERE MONTH(data_nascimento) = 7;
```

3. Quais produtos possuem embalagem "PET" e preço maior que R$ 15,00?

``` sql
SELECT *
FROM produtos
WHERE embalagem = 'PET'
AND preco > 15;
```

<br>

## Consultas condicionais
Próxima Atividade

Eduarda está analisando uma base de dados de jogos de vôlei e recebeu uma série de consultas escritas na linguagem SQL. Quais expectativas de Eduarda estão alinhadas à execução correta dos comandos utilizando o SQL Server?

**Selecione 2 alternativas**

- [ ] O código abaixo traz os times que estão depois da palavra CRUZEIRO na ordem alfabética.
``` sql
SELECT * FROM [Times] WHERE [Nome] < ‘CRUZEIRO’;
```

- [x] Será mostrado todos os jogadores e suas informações registradas na base de dados que não são da posição líbero.
``` sql
SELECT * FROM Jogadores
WHERE Posicao <> 'Líbero';
```

- [x] O código abaixo selecionará todas as linhas da tabela onde a partidas vencidas é maior que 10.
``` sql
SELECT * FROM [Campeonatos] WHERE [partidas vencidas] > 10;
```

- [ ] Executando o código abaixo aparecerá as partidas que ocorreram antes do dia 01 de janeiro de 2023.
``` sql
SELECT * FROM [Partidas] 
WHERE Data_Jogo >= '2023-01-01';
```

<br>

## Filtros compostos
1. Selecione o nome e bairro das pessoas cujo bairro seja Copacabana ou Tijuca

``` sql
SELECT nome, bairro
FROM clientes
WHERE bairro = 'Copacabana' OR bairro = 'Tijuca';
```

2. Podemos considerar outro cenário, em que desejamos conhecer as pessoas clientes de São Paulo que realizaram apenas uma compra.

``` sql
SELECT *
FROM clientes
WHERE estado = 'SP' AND primeira_compra = 1;
```

<br>

## Desafio: informações específicas
Para praticar ainda mais a utilização de filtros no SQL, te desafio a trazer as consultas abaixo:

1 - Liste os vendedores que possuem comissão menor ou igual a 8%.

``` sql
SELECT DISTINCT(vendedor)
FROM vendedores
WHERE percentual_comissao < 0.08;
```

2 - Liste os produtos que custam menos de 6 reais e estão disponíveis em lata.

``` sql
SELECT DISTINCT(produto)
FROM produtos
WHERE valor < 6
AND embalagem = 'Lata';
```

3 - Mostre todos os clientes que não são de São Paulo nem do Rio de Janeiro.

``` sql
SELECT DISTINCT(cliente)
FROM clientes
WHERE estado <> 'SP' AND estado <> 'RJ';
-- WHERE NOT (estado = 'SP' OR estado = 'RJ')
```

<br>

## Alterando as informações
1. Os sucos no formato lata estão em promoção. Como poderíamos executar essa alteração no preço da lista no nosso banco de dados, alterando todos os preços dos sucos em lata, aplicando uma promoção de 10%?

``` sql
UPDATE produtos
SET preco = preco * 0.9
WHERE embalagem = 'Lata';
```

2. A equipe de engenharia identificou um erro na nossa base de dados: um produto específico foi registrado com o preço e tipo de embalagem errados. Nos foi passado o código do produto, `1088126`, que usaremos para fazer essa modificação. Ele consta como embalagem PET, mas deveria ser do tipo garrafa. Além disso, o seu preço oficial não é R$ 7,00, e sim R$ 8,10.

``` sql
UPDATE produtos
SET preco = 8.1, embalagem = 'Garrafa'
WHERE codigo = '1088126';
```

3. A equipe de engenharia nos forneceu o código de produto `1004327` para ser deletado.

``` sql
DELETE FROM produtos
WHERE codigo = '1004327';
```

<br>

## Deletando informações
Esther é cientista de dados na área de RH de uma multinacional e precisou realizar uma alteração na tabela `TB_FUNCIONARIOS` na qual a coluna CPF é chave primária. Para realizar essa ação ela usou o código abaixo:

``` sql
DELETE FROM TB_FUNCIONARIOS  WHERE CPF = '757.170.810-90';
Copiar código
O que aconteceu após Esther executar este código?
```

Os dados da linha que contém o cpf '757.170.810-90' será excluida

<br>

