# Projeto Final 2 - WINDFARM

Projeto realizado no curso "*Formação Engenharia de Dados: Domine Big Data!*".

## Objetivo 🎯
1. Simular um ambiente de coleta e processamento de dados vindos de 3 sensores presentes em uma fazenda de produção de energia eólica;
2. Cada sensor é representado por um produtor, que gera dados a cada 10 segundos;
3. Os dados gerados devem ser enviados para um bucket S3 via Streaming;
4. Os dados armazenados no bucket S3 devem ser processados e armazenados em um Data Lake (outro bucket S3);

## Diagrama 📋

![Diagrama](diagrama.png)

## Requisitos 📄
- Credenciais de segurança da AWS (chaves de acesso);
- Produtores de dados desenvolvidos em Python (presentes nos arquivos do repositório);
- Kinesis Data Stream para coletar os dados e Kinesis Data Firehose para entrega destes dados em um destino;
- Bucket S3 para armazenar os dados gerados;
- Glue Crawler para analisar os schemas dos dados;
- Glue Job para processar estes dados e armazená-los no Data Lake;

## Desenvolvimento 👨🏻‍💻
### 1️⃣ Primeira etapa - Preparação de ambiente e armazenamento dos dados gerados
1. Criação dos produtores, presentes nos arquivos *Produtor_NOMEDOPRODUTOR* neste repositório, desenvolvidos em Python;
2. Linkar os produtores ao Kinesis Data Stream para receber os dados;
3. Linkar o Kinesis Data Stream ao Kinesis Data Firehose para entregar os dados ao bucket S3;

### 2️⃣ Segunda etapa - Glue Crawler, Glue Job e Athena
1. Utilizar o Glue Crawler para capturar os schemas dos dados armazenados no bucket S3;
2. Criar um Glue Job para armazenar os dados em um Data Lake (outro bucket S3), sem qualquer tipo de modificação neles;
3. Utilizar o Athena para visualização dos dados do Data Lake;