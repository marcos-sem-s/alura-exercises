## Praticando o comando INSERT
Agora,é necessário inserir um novo produto na tabela "Produtos" da base de dados "Sucos_Venda".

O produto é um suco de laranja, com as seguintes características:

- Código do produto: 1040107
- Nome do produto: "Light 350 ml - Melancia"
- Embalagem: Lata
- Tamanho: 350 ml
- Sabor: Melancia
- Preço de lista: R$ 4,56

``` sql
INSERT INTO produtos VALUES (
    '1040107',
    'Light 350 ml - Melancia',
    'Lata',
    '350 ml',
    'Melancia',
    4.56
);
```

<br>

## Limitações da inserção
Milena precisa registrar um novo cliente da sua empresa diretamente no banco de dados gerenciado pelo SQL Server. Levando em consideração a TABELA DE CLIENTES abaixo, quais operações podem ser realizadas por Milena?

(![captura de tela que destaca as informações de uma tabela de clientes. Essa tabela possui 14 colunas nomeadas da seguinte forma: cpf do tipo char(11), nome do tipo varchar(100), rua do tipo varchar(150), complemento do tipo varchar(150), bairro do tipo varchar(50), cidade do tipo varchar (50), estado do tipo char(2), cep do tipo char(8), data de nascimento do tipo date, idade do tipo smallint, sexo do tipo char(1), limite de credito do tipo money, volume de compra do tipo float e, por último, a primeira compra do tipo bit, Todas as colunas podem receber nulos, exceto o campo CPF.](img/image01.png))

- [x] O cliente nasceu no dia 20 de janeiro de 1987 e a data de nascimento do cliente deve ser inserida no formato AAAA-MM-DD, ou seja, 1987-01-20.
- [x] Se esse cliente já tiver comprado na empresa é possível inserir FALSE ou 0 na coluna PRIMEIRA COMPRA, caso contrário pode ser inserido TRUE ou 1.
- [ ] Milena ainda não sabe o CPF do novo cliente e isso não a impede de inseri-lo no banco de dados, pois ela pode deixar de preencher essa informação.
- [ ] O novo cliente não possui crédito disponível, por isso no campo Limite de crédito pode ser inserido a informação “não possui”.

<br>

## Inserindo múltiplas linhas
1. Imagine que a Frutally está lançando uma nova linha de sucos com sabores exóticos. Crie um script SQL para inserir os seguintes produtos na tabela de produtos:

- 1099999: "Frutally Tropical - 1 Litro - Maracujá", "PET", "1 Litro", "Maracujá", 8.50
- 1100000: "Frutally Tropical - 1 Litro - Manga", "PET", "1 Litro", "Manga", 9.20
- 1100001: "Frutally Tropical - 1 Litro - Acerola", "PET", "1 Litro", "Acerola", 7.90

``` sql
INSERT INTO produtos VALUES
('1099999', 'Frutally Tropical - 1 Litro - Maracujá', 'PET', '1 Litro', 'Maracujá', 8.50),
('1100000', 'Frutally Tropical - 1 Litro - Manga', 'PET', '1 Litro', 'Manga', 9.20),
('1100001', 'Frutally Tropical - 1 Litro - Acerola', 'PET', '1 Litro', 'Acerola', 7.90);
```

2. A Frutally está expandindo suas operações para um novo bairro, e você precisa inserir os dados de três novos clientes que moram lá:

- 00384393666: "Ana Maria", "Rua das Flores", "Número 123", "Jardim das Flores", "RJ", "20000000", "1980-05-15", 42, "F", 150000, 2500.00, 1
- 00384393777: "Pedro Silva", "Rua dos Pássaros", "Número 456", "Jardim das Flores", "RJ", "20000000", "1990-08-20", 32, "M", 200000, 3000.00, 1
- 00384393888: "Joana Santos", "Rua dos Girassóis", "Número 789", "Jardim das Flores", "RJ", "20000000", "1975-12-01", 46, "F", 180000, 2800.00, 0

``` sql
INSERT INTO clientes VALUES
('00384393666', 'Ana Maria', 'Rua das Flores', 'Número 123', 'Jardim das Flores', 'RJ', '20000000', '1980-05-15', 42, 'F', 150000, 2500.00, 1),
('00384393777', 'Pedro Silva', 'Rua dos Pássaros', 'Número 456', 'Jardim das Flores', 'RJ', '20000000', '1990-08-20', 32, 'M', 200000, 3000.00, 1),
('00384393888', 'Joana Santos', 'Rua dos Girassóis', 'Número 789', 'Jardim das Flores', 'RJ', '20000000', '1975-12-01', 46, 'F', 180000, 2800.00, 0);
```

<br>

## Desafio: Incluindo vendedores
Agora que já aprendemos a inserir diversos dados ao mesmo tempo em uma tabela, chegou o momento de colocarmos a mão na massa.

Na empresa surgiu uma nova demanda. Algumas informações específicas precisam ser inseridas, porém há dificuldades para realizar essa tarefa de maneira eficiente e sem erros.

Como podemos de uma única vez auxiliar o time inserindo os novos dados nessa tabela de vendedores?

Para essa ação, considere os seguintes dados:

| Matrícula | Nome | Comissão |
| --------- | ---- | -------- |
| 00236 | Cláudia Morais | 8% |
| 00237	| Marcela Ferreira | 9% |
| 00238	| Márcio Almeida | 8% |

``` sql
INSERT INTO vendedores VALUES
('00236', 'Cláudia Morais', 0.08),
('00237', 'Marcela Ferreira', 0.09),
('00238', 'Márcio Almeida', 0.08);
```

<br>

## Inserindo fora da ordem
Escreva o código SQL para inserir esses dois produtos na tabela "PRODUTOS", mas com a ordem dos campos diferente da ordem da tabela. Por exemplo, imagine que você precisa inserir o "PRECO DE LISTA" antes do "SABOR".

Produto 1:

- Código do Produto: 5449310
- Nome do Produto: "Frescor do Verão - 350 ml - Limão"
- Embalagem: "Lata"
- Tamanho: "350 ml"
- Preço de Lista: 2.45
- Sabor: "Limão"

Produto 2:

- Código do Produto: 1078680
- Nome do Produto: "Frescor do Verão - 350 ml - Manga"
- Embalagem: "Lata"
- Tamanho: "350 ml"
- Preço de Lista: 3.18
- Sabor: "Manga"

``` sql
INSERT INTO produtos 
    (codigo_produto, nome_produto, embalagem, tamanho, preco_lista, sabor) 
VALUES
    ('5449310', 'Frescor do Verão - 350 ml - Limão', 'Lata', '350 ml', 2.45, 'Limão'),
    ('1078680', 'Frescor do Verão - 350 ml - Manga', 'Lata', '350 ml', 3.18, 'Manga')
```

<br>

## Desafio: preenchendo tabelas
Agora que conhecemos melhor a inserção de dados nas tabelas, podemos preenchê-las com as outras informações da empresa.

Neste desafio, você precisa construir um código em SQL para inserir produtos e clientes em suas respectivas tabelas. Para executar essa ação, você deve se basear nessa planilha.

``` sql
INSERT INTO clientes
VALUES
('1471156710', 'Erica Carvalho', 'R. Iriquitia', Null, 'Jardins', 'SP', '80012212', '1990-09-01', 32, 'F', 1700000000, 24500, 0), 
('19290992743', 'Fernando Cavalcante', 'R. Dois de Fevereiro', Null, 'Agua Santa', 'RJ', '22000000', '2000-02-12', 23, 'M', 1000000000, 20000, 1), 
('2600586709', 'Cesar Teixeira', 'Rua Conde de Bonfim', Null, 'Tijuca', 'RJ', '22020001', '2000-03-12', 23, 'M', 1200000000, 22000, 0), 
('3623344710', 'Marcos Nogueira', 'Av. Pastor Martin Luther King Junior', Null, 'Inhauma', 'RJ', '22002012', '1995-01-13', 28, 'M', 1100000000, 22000, 1), 
('492472718', 'Eduardo Jorge', 'R. Volta Grande', Null, 'Tijuca', 'RJ', '22012002', '1994-07-19', 28, 'M', 750000000, 9500, 1), 
('50534475787', 'Abel Silva', 'Rua Humaita', Null, 'Humaita', 'RJ', '22000212', '1995-09-11', 27, 'M', 1700000000, 26000, 0), 
('5576228758', 'Petra Oliveira', 'R. Benicio de Abreu', Null, 'Lapa', 'SP', '88192029', '1995-11-14', 27, 'F', 700000000, 16000, 1), 
('5648641702', 'Paulo Cesar Mattos', 'Rua Helio Beltrao', Null, 'Tijuca', 'RJ', '21002020', '1991-08-30', 31, 'M', 1200000000, 22000, 0), 
('5840119709', 'Gabriel Araujo', 'R. Manuel de Oliveira', Null, 'Santo Amaro', 'SP', '80010221', '1985-03-16', 37, 'M', 1400000000, 21000, 1), 
('7771579779', 'Marcelo Mattos', 'R. Eduardo Luis Lopes', Null, 'Bras', 'SP', '88202912', '1992-03-25', 30, 'M', 1200000000, 20000, 1), 
('8502682733', 'Valdeci da Silva', 'R. Srg. Edison de Oliveira', Null, 'Jardins', 'SP', '82122020', '1995-10-07', 27, 'M', 1100000000, 19000, 0), 
('8719655770', 'Carlos Eduardo', 'Av. Gen. Guedes da Fontoura', Null, 'Jardins', 'SP', '81192002', '1983-12-20', 39, 'M', 2000000000, 24000, 0), 
('9283760794', 'Edson Meilelles', 'R. Pinto de Azevedo', Null, 'Cidade Nova', 'RJ', '22002002', '1995-10-07', 27, 'M', 1500000000, 25000, 1), 
('94387575700', 'Walber Lontra', 'R. Cel. Almeida', Null, 'Piedade', 'RJ', '22000201', '1989-06-20', 33, 'M', 600000000, 12000, 1), 
('95939180787', 'Fabio Carvalho', 'R. dos Jacarandas da Peninsula', Null, 'Barra da Tijuca', 'RJ', '22002020', '1992-01-05', 31, 'M', 900000000, 18000, 1);

INSERT INTO produtos
VALUES
('1042712', 'Linha Citros - 700 ml - Limão', 'Garrafa', 'Limão', '700 ml', 4.90), 
('788975', 'Pedaços de Frutas - 1, 5 Litros - Maça', 'PET', 'Maça', '1, 5 Litros', 18.01), 
('1002767', 'Videira do Campo - 700 ml - Cereja/Maça', 'Garrafa', 'Cereja/Maça', '700 ml', 8.41), 
('231776', 'Festival de Sabores - 700 ml - Açai', 'Garrafa', 'Açai', '700 ml', 13.31), 
('479745', 'Clean - 470 ml - Laranja', 'Garrafa', 'Laranja', '470 ml', 3.76), 
('1051518', 'Frescor do Verão - 470 ml - Limão', 'Garrafa', 'Limão', '470 ml', 3.29), 
('1101035', 'Linha Refrescante - 1 Litro - Morango/Limão', 'PET', 'Morango/Limão', '1 Litro', 9.01), 
('229900', 'Pedaços de Frutas - 350 ml - Maça', 'Lata', 'Maça', '350 ml', 4.21), 
('1086543', 'Linha Refrescante - 1 Litro - Manga', 'PET', 'Manga', '1 Litro', 11.01), 
('695594', 'Festival de Sabores - 1, 5 Litros - Açai', 'PET', 'Açai', '1, 5 Litros', 28.51), 
('838819', 'Clean - 1, 5 Litros - Laranja', 'PET', 'Laranja', '1, 5 Litros', 12.01), 
('326779', 'Linha Refrescante - 1, 5 Litros - Manga', 'PET', 'Manga', '1, 5 Litros', 16.51), 
('520380', 'Pedaços de Frutas - 1 Litro - Maça', 'PET', 'Maça', '1 Litro', 12.01), 
('1041119', 'Linha Citros - 700 ml - Lima/Limão', 'Garrafa', 'Lima/Limão', '700 ml', 4.90), 
('243083', 'Festival de Sabores - 1, 5 Litros - Maracujá', 'PET', 'Maracujá', '1, 5 Litros', 10.51), 
('394479', 'Sabor da Montanha - 700 ml - Cereja', 'Garrafa', 'Cereja', '700 ml', 8.40), 
('746596', 'Light - 1, 5 Litros - Melancia', 'PET', 'Melancia', '1, 5 Litros', 19.50), 
('773912', 'Clean - 1 Litro - Laranja', 'PET', 'Laranja', '1 Litro', 8.01), 
('826490', 'Linha Refrescante - 700 ml - Morango/Limão', 'Garrafa', 'Morango/Limão', '700 ml', 6.31), 
('723457', 'Festival de Sabores - 700 ml - Maracujá', 'Garrafa', 'Maracujá', '700 ml', 4.91), 
('812829', 'Clean - 350 ml - Laranja', 'Lata', 'Laranja', '350 ml', 2.80), 
('290478', 'Videira do Campo - 350 ml - Melancia', 'Lata', 'Melancia', '350 ml', 4.56), 
('783663', 'Sabor da Montanha - 700 ml - Morango', 'Garrafa', 'Morango', '700 ml', 7.70), 
('235653', 'Frescor do Verão - 350 ml - Manga', 'Lata', 'Manga', '350 ml', 3.85), 
('1002334', 'Linha Citros - 1 Litro - Lima/Limão', 'PET', 'Lima/Limão', '1 Litro', 7.00), 
('1013793', 'Videira do Campo - 2 Litros - Cereja/Maça', 'PET', 'Cereja/Maça', '2 Litros', 24.01), 
('1096818', 'Linha Refrescante - 700 ml - Manga', 'Garrafa', 'Manga', '700 ml', 7.71), 
('1022450', 'Festival de Sabores - 2 Litros - Açai', 'PET', 'Açai', '2 Litros', 38.01);
```

<br>

## Maneiras de inserir informações
Manuela é desenvolvedora junior em uma empresa de consultoria e está implementando um modelo relacional para seu cliente Filmefix, uma empresa de streaming de filmes e séries. Usando a linguagem SQL com o SQLServer, ela já criou todas as tabelas. Entretanto, algumas informações ficaram pendentes para serem inseridas.

Como a Manuela pode realizar a inserção de linhas na tabela Filmes, que está localizada logo abaixo? Selecione 3 alternativas

| Id_filme | Nome | Lançamento | Duração | Gênero |
| -------- | ---- | ---------- | ------- | ------ |
| 1 | Toy Story | 1995-12-22 | 81 | Aventura |
| 2 | O Silêncio dos Inocentes | 1991-05-17 | 118 | Suspense |
| 3 | Coringa | 2019-10-03 | 122 | Drama |

- [x]
``` sql
{SQL}
INSERT INTO FILMES VALUES
(1, 'Toy Story', '1995-12-22' , 81, 'Aventura'),
(2, 'O Silêncio dos Inocentes', '1991-05-17' , 118, 'Suspense'),
(3, 'Coringa', '2019-10-03' , 122, 'Drama');
```

- [x]
``` sql
INSERT INTO  [FILMES]
([Id_filme], [Nome], [Genero], [Lancamento], [Duracao] )  
VALUES
(1, 'Toy Story', 'Aventura', '1995-12-22', 81),
(2, 'O Silêncio dos Inocentes', 'Suspense', '1991-05-17', 118),
(3, 'Coringa', '2019-10-03', 'Drama', 122);
```

- [ ]
``` sql
INSERT INTO FILMES ([Nome], [Genero], [Lancamento], [Duracao], [Id_filme] ) 
VALUES
('Toy Story', 'Aventura', '1995-12-22', 81, 1),
('O Silêncio dos Inocentes', 'Suspense', '1991-05-17', 118, 2),
('Coringa', 'Drama', '2019-10-03', 122, 3); 
```

- [x]
``` sql
INSERT INTO [FILMES] VALUES
(1, 'Toy Story', '1995-12-22', 81, 'Aventura'); 
INSERT INTO [FILMES] VALUES
(2, 'O Silêncio dos Inocentes', '1991-05-17' , 118, 'Suspense'); 
INSERT INTO [FILMES] VALUES
(3, 'Coringa', '2019-10-03', 122, 'Drama'); 
```

<br>

## Restrição de chave primária
Para testar a restrição de chave primária, podemos usar o comando INSERT INTO para inserir dados em uma tabela.

**Exercício**

Tente inserir um valor nulo (NULL) na coluna que define a chave primária. O que acontece? Erro
Tente inserir um valor duplicado na coluna que define a chave primária. O que acontece? Erro
