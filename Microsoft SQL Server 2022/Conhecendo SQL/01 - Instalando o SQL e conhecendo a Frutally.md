## Instalação SGBD & Preparando o ambiente
Para testar seus conhecimentos sobre a instalação do SGBD e a sua preparação do ambiente, que tal um exercício?

1. Crie uma pasta: Crie uma pasta no diretório C:/ para guardar os arquivos do SQL Server.
2. Baixe o SQL Server: Acesse o site da Microsoft e baixe a versão de desenvolvedor do SQL Server 2022.
3. Selecione "Baixar mídia": Na instalação, escolha a opção "Baixar mídia".
4. Defina o idioma e o diretório: Selecione o idioma Português, o tipo de pacote CAB e o diretório da pasta que você criou (C:\SQLServer22).
5. Execute o arquivo: Após o download, abra a pasta e execute o arquivo "SQLServer2022-DEV-x64-PTB.exe".
6. Inicie a instalação: Na janela que abrir, clique em "Instalação" e escolha a opção "Nova instalação autônoma do SQL Server ou adicionar recursos a uma instalação existente".
7. Aceite os termos: Aceite os termos de licença.
8. Verifique os requisitos: O programa fará uma verificação dos requisitos do seu computador.
9. Desmarque os serviços do Azure: Desmarque a opção "Extensão do Azure para SQL SE".
10. Selecione os serviços: Marque a opção "Serviços de Mecanismo de Banco de Dados".
11. Mantenha a instância padrão: Mantenha a opção "instância padrão" selecionada.
12. Configure a autenticação: Na etapa de autenticação, marque a opção "misto" e adicione o usuário atual do Windows.
13. Conclua a instalação: Revise as configurações e clique em "Instalar".

Pronto! Após a instalação, você terá o SQL Server 2022 configurado na sua máquina.

<br>

## Instalação IDE
Para testar seus conhecimentos sobre a instalação do SSMS e a conexão ao servidor, que tal um exercício?

1. Instale o SSMS:
    - Acesse o site da Microsoft e baixe o SSMS.
    - Execute o arquivo .exe e siga as instruções da instalação.
    - Dica: Escolha um local de instalação para o SSMS.
2. Conecte-se ao servidor SQL Server:
    - Abra o SSMS e escolha a opção de conexão.
    - Dica: Experimente conectar usando as duas formas de autenticação: Autenticação do Windows e Autenticação do SQL Server.
3. Verifique a conexão:
    - Observe as pastas que aparecem no menu esquerdo do SSMS.
    - Dica: Se você conseguir ver as pastas, significa que a conexão foi estabelecida com sucesso!

<br>

## SSMS vs SQLServer22
Mariana está começando seus estudos de SQLServer e observou a nova versão para 2022. Antes de começar seus códigos logo começou a instalação de dois componentes: o SQL Server Management Studio (SSMS) e o SQLServer22.

Qual a principal diferença entre esses dois componentes instalados por Mariana?

- [x] O SQL Server Management Studio é uma ferramenta de desenvolvimento, enquanto o SQL Server 22 é uma ferramenta de gerenciamento de banco de dados.
- [ ] O SQL Server Management Studio é usado para desenvolver bancos de dados e escrever consultas SQL, enquanto o SQL Server 22 é usado para gerenciar e administrar bancos de dados existentes. Embora os dois produtos sejam relacionados e sejam usados em conjunto, eles possuem objetivos diferentes e atendem a necessidades diferentes no ciclo de vida do banco de dados.
- [ ] O SQL Server 22 é uma versão do SGBD distribuída pela Microsoft que pode ser integrada pela IDE do SSMS, que, por outro lado, é produzida por outra empresa.
- [ ] O SQL Server 22 é uma ferramenta de desenvolvimento, enquanto o SQL Server Management Studio é uma ferramenta de gerenciamento de banco de dados.
- [ ] O SQL Server 22 é uma versão mais recente do SQL Server Management Studio e tem sua instalação em etapas que contém dois componentes.
