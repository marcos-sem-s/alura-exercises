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



<br>

