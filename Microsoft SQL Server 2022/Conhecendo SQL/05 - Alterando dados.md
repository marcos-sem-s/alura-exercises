## Filtros no SQL
Ainda sobre a personalização das consultas, lembre-se que nos passos anteriores criamos uma consulta que exibe o nome, CPF e estado de cada um dos clientes. Supondo que quiséssemos apenas os clientes que realizaram a primeira compra para direcionar uma campanha de marketing para esse público específico, como poderíamos construir essa consulta?

``` sql
SELECT nome AS nome_cliente, estado AS uf, primeira_compra
FROM clientes
WHERE primeira_compra = 1;
```

<br>

## Filtros em vários tipos



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
