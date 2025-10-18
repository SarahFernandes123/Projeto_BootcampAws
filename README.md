# Projeto_BootcampAws
Projeto de arquitetura serverless plataforma de Streaming de Vídeo Sob Demanda (VOD) realizado para o Bootcamp da AWS.

## Sistema de Streaming de Vídeo On-Demand na AWS

### Visão geral do projeto
##### Este projeto consiste em uma arquitetura de um sistema de Streaming de Vídeo Sob Demanda (Video On-Demand - VOD) utilizando os principais serviços Serverless da Amazon Web Services (AWS). O objetivo é construir uma plataforma altamente escalável, de baixa latência e custo-otimizada para ingestão, processamento, armazenamento e distribuição de conteúdo de vídeo.

### Tecnologias utilizadas da AWS
##### S3 - Utilizado para armazenamento de alta durabilidade dos vídeos de forma bruta;
##### AWS Lambda - Para a orquestraçaõ das transcodificação e metadados;
##### AWS Elemental MediaConvert - Conversão do vídeo em diversos formatos e bitrates (qualdiade);
##### DynamonDB - Banco de dados NoSQL para o armazenamento dos metadados;
##### API CloudFront - Garante que o usuário recebe o vídeo com baixa latência e com qualidade; 

### Fluxo de Ingestão e Processamento (Ingestion & Processing)
##### 1. Upload: Customer envia o arquivo para um bucket de origem no S3. 
##### 2. Disparo do processo: O novo arquivo no S3 dispara um Lambda; 
##### 3. Transcodificação: o Lambda solicita o AWS Elemental MediaConvert a criação de múltiplas criações dos vídeos; 
##### 4. Armazenamento do Resultado: As novas versões são enviadas para um bucket S3 de destino; 
##### 5. Registro dos Metadados: O lambda armazena as informações dos vídeos e os arquivos transcodificados em um DynamoDB. 
