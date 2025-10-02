# Análise de Dados: Casos de Suicídio no Brasil 🎗️

## 1. 👥 Equipe
* Caroline Cortez
* Carlos Ryan
* Emerson Oliveira
* Gisely Karla
* Laila Guedes
* Nathalia Kopke
* Vaneza Magalhães

## 2. Documentação
* [Dashboard](https://www.google.com.br)
* [Apresentação](https://www.google.com.br)

## 3. Contexto do problema de negócio

O suicídio representa um grave e complexo **desafio de saúde pública** no Brasil. Neste cenário, a Atenção Primária à Saúde (APS), como a principal porta de entrada do Sistema Único de Saúde (SUS) e o ponto de contato mais próximo da comunidade, desempenha um **papel fundamental na prevenção**.

No mês de **Setembro Amarelo** (mês dedicado à prevenção do suicídio), a nossa equipe responsável pelas campanhas e estratégias de saúde mental na linha de APS identificou uma lacuna:
* As campanhas de prevenção são, frequentemente, genéricas e não direcionadas aos grupos de maior risco ou às épocas de maior ocorrência de casos.

Nesse sentido, é essencial obter uma **visão analítica e detalhada** sobre a distribuição, os padrões e os fatores associados aos casos de suicídio no Brasil.

Este projeto de análise de dados visa nortear o planejamento estratégico das ações de prevenção ao suicídio e promoção da saúde mental. A análise garantirá que os recursos sejam aplicados de forma eficaz e direcionada, maximizando o impacto da APS onde a necessidade é maior.

## 4. Objetivo

O objetivo deste projeto é transformar dados brutos sobre suicídio no Brasil (2014-2018) em insights para apoiar no planejamento das ações de prevenção da Atenção Primária à Saúde (APS).

A análise busca fornecer um mapeamento do problema, permitindo que as equipes de saúde possam:

* Identificar os grupos de maior risco (por idade, sexo, raça);
* Analisar a sazonalidade dos casos, descobrindo se há meses ou épocas do ano com maior ocorrência;
* Otimizar a alocação de recursos (equipes e campanhas), focando a intervenção onde o potencial de impacto é maior.

### 💡 Perguntas norteadoras do projeto
**1. Existe diferença na taxa de suicídio entre os sexos (masculino e feminino)?**

**2. Há variação na incidência de suicídio relacionada à cor/raça?**

**3. Qual a distribuição de casos por faixa etária, e quais são as idades ou grupos etários de maior frequência?**

**4. Há evidências de sazonalidade? Existe algum mês ou período específico do ano que registra uma frequência ou quantidade mais alta de casos?**

* ADICIONAR MAIS PERGUNTAS

## Metodologia

## 5. Ferramentas e Tecnologias
* Looker Studio
* BigQuery
* Python
* Google Colab
* Canva

## 6. Fonte de Dados
* [Dataset | Dados de Suicídio no Brasil 2014 a 2018 (Kaggle)](https://www.kaggle.com/datasets/psicodata/dados-de-suicdio-no-brasil-2014-a-2018/data)
* SIM - Sistema de Informação sobre Mortalidade https://pysus.readthedocs.io/pt/latest/databases/SIM.html
* Período dos dados: 2014 a 2022

## 7. Como rodar o projeto

## 8. Estrutura do Repositório

### Pré-processamento de dados:
Descreva como os dados foram obtidos e qualquer processo de limpeza ou transformação realizado.
* Coleta e Ingestão: Selecionaram datasets, integraram múltiplas fontes no BigQuery
* Limpeza e Transformação: Trataram dados, criaram variáveis derivadas
* Análise Exploratória: Descobriram padrões, formularam hipóteses
* Modelagem Estatística: Testaram hipóteses, construíram modelos preditivos
---
* Definir o Schema**: Criar as tabelas 
* Ingerir os Dados**: Inserir os dados brutos fornecidos nas tabelas.
* Analisar os Dados**: Escrever consultas SQL para responder a perguntas de negócio.
* Criar uma View**: Construir views para simplificar análises futuras.

## Métodos e técnicas:
Documente as técnicas e metodologias usadas na análise.

## Conclusões 
Apresenta os principais resultados obtidos a partir da análise de dados. Sumariza as conclusões tiradas do projeto, incluindo insights importantes, descobertas relevantes e possíveis 
* Principais descobertas
* Insights
* Recomendações
  
## Limitações 
Identifique e descreva quaisquer limitações ou desafios encontrados durante o projeto. Sugira possíveis próximos passos para estender ou aprimorar o projeto de análise de dados.**
* Desafios enfrentados
* período dos dados (o ideal seria dados mais atuais)
  
## Referências
* [Notícia G1 | Brasil tem uma tentativa de suicídio ou autolesão entre adolescentes a cada 10 minutos](https://g1.globo.com/saude/saude-mental/noticia/2025/09/22/brasil-tem-uma-tentativa-de-suicidio-ou-autolesao-entre-adolescentes-a-cada-10-minutos.ghtml)
* [OPAS | Atenção Primária à Saúde](https://www.paho.org/pt/topicos/atencao-primaria-saude)
