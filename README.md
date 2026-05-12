
# Pipeline Serverless de Ingestão de Dados - AWS

Este repositório contém a documentação e a arquitetura de um pipeline automatizado de ingestão e processamento de dados na AWS (Amazon Web Services), utilizando uma abordagem 100% serverless e orientada a eventos.

## 📌 Arquitetura do Projeto

O fluxo de dados foi desenhado utilizando a ferramenta Draw.io e segue a estrutura abaixo:

![Diagrama da Arquitetura](drawio.gif)

### Fluxo de Funcionamento:
1. **Origem:** Um operador ou sistema local interage com o **Sistema de Arquivos** para gerar um documento/dado.
2. **Upload:** O arquivo é transferido para a nuvem de forma programática através da interface de linha de comando (**AWS CLI**).
3. **Armazenamento:** O arquivo é depositado em um bucket do **Amazon S3** (Simple Storage Service).
4. **Gatilho (Trigger):** O upload do arquivo dispara um evento automático (`ObjectCreated`) no S3.
5. **Processamento:** O evento aciona uma função **AWS Lambda**, que executa o código de computação serverless para ler e processar o conteúdo do arquivo.
6. **Persistência:** Os dados extraídos e tratados são gravados de forma estruturada em uma tabela do **Amazon DynamoDB** (Banco de dados NoSQL).

---

## 🛠️ Tecnologias e Serviços Utilizados

*   **AWS CLI:** Para automação de transferência de arquivos local-nuvem.
*   **Amazon S3:** Armazenamento de objetos escalável e de alta disponibilidade.
*   **AWS Lambda:** Execução de código orientada a eventos sem gerenciamento de servidores.
*   **Amazon DynamoDB:** Banco de dados NoSQL de baixa latência para armazenamento dos dados finais.
*   **Draw.io:** Ferramenta utilizada para a modelagem visual da arquitetura.

---

## 🚀 Principais Vantagens desta Arquitetura

*   **Custos Otimizados (Pay-per-use):** Os recursos só são cobrados quando há execução (computação serverless).
*   **Escalabilidade Automática:** O pipeline suporta desde poucos arquivos até milhões de requisições simultâneas sem necessidade de intervenção manual.
*   **Alta Disponibilidade:** Utilização de serviços gerenciados nativos da AWS com replicação automática.

---

## ✒️ Autor

*   **Ariane** - [ConectAri](https://github.com)
