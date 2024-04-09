# 4.IMPLEMENTAÇÃO 

## 4.1. ETL 

A extração das bases de dados é realizada por API, sem necessidade de download local de arquivos, através de um arquivo JSON, composto por informações de acesso aos arquivos das CATS. 

Quatro códigos foram produzidos para esta etapa; um principal, “Main.py”; e três classes; “Download.py” 

### 3.1.1. Script Download.py 

O script (1) verifica a existência do arquivo acessado pela URL no local do projeto (ROOT_DIR). Caso não exista, é iniciado o download. (2) Caso o arquivo seja CSV, é feito o download e verificação da quantidade de colunas do arquivo, podendo ela ser 24 ou 25. (3) O arquivo é então movido para a pasta correspondente a quantidade de colunas. (4) Caso seja ZIP, o arquivo é aberto "virtualmente"(o download ainda não foi feito) e é feita a leitura dos arquivos que estão no ZIP. (5) O download do ZIP é realizado e seus arquivos são extraídos. (6) Caso contenha um arquivo .CSV e este arquivo, não esteja nos diretórios do projeto, a etapa 3 é realizada; (7) Ao final do processo, todos os arquivos que não sejam .CSV, são deletados. 

### 3.1.2. Script WorkWithFiles.py 

Realiza a montagem dos templates finais. Após o download dos arquivos, as pastas modelos terão diversos arquivos .CSV, sendo necessário juntá-los em dois arquivos finais. É então realizada a leitura de um arquivo por vez, executando correções de caracteres (utf-8) e substituição de alguns valores. Classificação e filtragem das colunas é finalmente realizada a fim de se adicionar um novo header para cada modelo, mantendo apenas as colunas necessárias para o resultado. 

### 3.1.3 Script ETL.py 

Esta classe é responsável por unificar o conteúdo dos dois templates em dataframes. Procedimentos de filtro de duplicatas são realizados. Também é responsável pela criação das tabelas fato e dimensão em arquivos .csv, assim como o schema para implementação no banco de dados. 

Sempre que chamada, irá efetuar a limpeza do banco já criado, ou criar um novo, caso instanciada passando como parâmetro outro schema. É criada uma tabela Fato com as chaves correspondentes para cada registro nas tabelas dimensão. 
