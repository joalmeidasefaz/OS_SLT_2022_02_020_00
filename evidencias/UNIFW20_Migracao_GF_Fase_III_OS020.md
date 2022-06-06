# [UNIFW20] - Migração GF Fase III 



## Objetivo

O objetivo desta terceira fase é a preparação do ambiente de Desenvolvimento bem como homologação para a implantação da última versão do GF após migração para o Framework .Net 4.8 e UniFW 2.0.



## Preparação do ambiente Com código GF atualizado e estável

Configuração do Visual Studio e criação de uma nova solução com os arquivos disponibilizados  do repositório.

Etapa 1: Instalação do Visual Studio 2017

- Aberto chamado de número 230845 no SGS para atualização versão Visual Studio 2013 para 2017 e ativação da chave na estação de trabalho.
- Chamado aberto em 13/05 e finalizado em 18/05.

Etapa 2: Baixar arquivos do repositório para criação de uma nova solução no Visual Studio

- O repositório fica em http://tfs.sefaz.ba.gov.br:8080/tfs/Fiscalizacao/GF/_versionControl?path=%24%2FGF
- Existe uma pasta chamada DLLs Oficial, nesta pasta estão as DLLs corretas do sistema, tivemos alguns problemas utilizando outros DLLs que estavam no sistema antes, principalmente em relação a parte de gerar relatórios, então recomendo que use as DLLs daí.
- Quanto a versão mais recente, ela está na pasta da versão 1.29 de homologação: http://tfs.sefaz.ba.gov.br:8080/tfs/Fiscalizacao/GF/_versionControl?path=%24%2FGF%2FHomologacao%2FV01.29.00





## Configuração de referencias para projeto UniFw 2.0

Após criar uma nova solução e baixar os arquivos do repositório, as referências "quebradas" do UNIFW foram substituídas pela versão mais recente. A imagem abaixo mostra as referências que foram substituídas:

![imagem](..\.attachments\referencias _unifw)

Criada uma nova pasta no projeto "UNIFW" e importada os arquivos. Após importação, as referências dos arquivos "quebrados" foram substituídos.

![image-20220602180036452](C:\Users\joalmeida\Desktop\OS20\.attachments\importacao_unifw_1.PNG)

Ao compilar a solução, o projeto apresentou erro no aplicativo Web.SEFAZ.GF.Web, alegando não encontrar o servidor de ISS.

![img](C:\Users\joalmeida\Desktop\OS20\.attachments\erro_ISS)

Para correção do problema apresentado, o arquivo web.config foi editado, alterando o parâmetro para "localhost", conforme imagem abaixo:



![imagem](C:\Users\joalmeida\Desktop\OS20\.attachments\arquivo_editado)



## Migração do projeto GF para framework 4.8

Editado a propriedade do arquivo SEFAZ.GF.Classes --> Aplicativo --> Estrutura de Destino --> .NET Framework 4.8

![image-20220602175716089](C:\Users\joalmeida\Desktop\OS20\.attachments\image-20220602175716089.png)



## Impeditivos Apresentados

Após a realização dos procedimentos acima e compilado o projeto, os erros abaixo foram apresentados, impedindo a continuidade das atividades.

Em contato com a equipe GF para suporte na correção do erro apresentado, foi feita a indicação dos analistas do projeto SIGAT, por conta de maior expertise no problema. Após análise, os analistas entenderam se tratar de erro de chave de conexão criptografada utilizada pelas aplicações para conexão com o banco de dados. Trata-se de um arquivo de registro do Windows.

Possíveis soluções a serem adotadas:

- Verificar na Wiki os chamados do antigo analista José Luiz para verificação de referências do problema apresentado;
- Consultar o analista Adalberto Correia sobre o histórico da OS relativa à migração do SIGAT, que possui os mesmos requisitos para execução do projeto
- Abrir chamado com equipe de AS, solicitando a instalação/configuração do arquivo de registro do Windows para configuração do ambiente.

![image-20220602180351099](C:\Users\joalmeida\Desktop\OS20\.attachments\erro_projeto)

## Conclusão

Na próxima OS24 será dado sequência à resolução dos problemas encontrados, além de realização dos testes de funcionamento da projeto após migração.

