## Criação do ambiente de trabalho
1. Faça o download do arquivo Arquivos.zip.

2. Crie um diretório e copie o arquivo baixado.

3. Veja os arquivos de script.

4. Vá no SQL Server Management Studio e conecte-se ao seu servidor. Após isso, na árvore à esquerda, clique com o botão da direita do mouse sobre Banco de Dados e selecione a opção Novo Banco de Dados.

5. Nomeie o banco de dados como SUCOS_FRUTAS. Clique em OK.

6. Clique em Arquivo/Abrir e escolha a opção Arquivo.

7. Escolha o script Cria_Banco.sql e clique em Abrir.

8. Comente as linhas de DROP das tabelas.

9. Certifique se o banco selecionado está correto.

10. Clique no ícone Executar.

11. Novamente clique em Arquivo/Abrir e escolha a opção Arquivo.

12. Escolha o script Carga_Cadastros.sql e clique em Abrir.

13. Clique no ícone Executar.

14. Mais uma vez clique em Arquivo/Abrir e escolha a opção Arquivo.

15. Escolha o script Carga_Notas.sql e clique em Abrir.

16. Clique no ícone Executar.

17. Para carregar as os itens das notas fiscais clique em Arquivo/Abrir e escolha a opção Arquivo.

18. Escolha o script Carga_Itens_Notas.sql e clique em Abrir.

19. Clique no ícone Executar.

20. Verifique se houve a carga correta das tabelas. Usando os comandos:

``` sql
SELECT COUNT(*) FROM TABELA_DE_CLIENTES;
SELECT COUNT(*) FROM TABELA_DE_PRODUTOS;
SELECT COUNT(*) FROM TABELA_DE_VENDEDORES;
SELECT COUNT(*) FROM NOTAS_FISCAIS;
SELECT COUNT(*) FROM ITENS_NOTAS_FISCAIS;
```

## 