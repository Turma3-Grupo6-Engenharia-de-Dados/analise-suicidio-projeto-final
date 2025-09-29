# Análise de Dados: Casos de Suicídio no Brasil 

## 1. 👥 Equipe
* Caroline Cortez
* Carlos Ryan
* Emerson Oliveira
* Gisely Karla
* Laila Guedes
* Nathalia Kopke
* Vaneza Magalhães

## 2. Documentação
* link Dashboard
* link Apresentação
* link Documentação Notion (?)

## 3. Contexto do problema de negócio

O suicídio é uma questão de saúde pública no Brasil, a cada dez minutos, um adolescente comete algum tipo de autolesão ou tenta tirar a própria vida no Brasil.

No mês de Setembro Amarelo (mês dedicado à prevenção do suicídio), a nossa equipe responsável pelas campanhas e estratégias de saúde mental na linha de APS identificou a necessidade de uma abordagem baseada em dados.

A Atenção Primária à Saúde (APS) é a porta de entrada principal de um sistema de saúde, como o SUS, focada na promoção, prevenção, diagnóstico, tratamento e reabilitação de problemas de saúde individuais, familiares e coletivos. A APS prioriza o contato direto e contínuo com a comunidade, atuando de forma abrangente e próxima para atender até 90% das necessidades de saúde da população, agindo sobre os determinantes sociais da saúde e empoderando os indivíduos e comunidades.

No contexto de análise dos dados (2014-2018), as campanhas de prevenção são genéricas e não direcionadas aos grupos de maior risco ou às regiões mais afetadas.

## 4. Objetivo

O objetivo deste projeto é transformar dados brutos sobre suicídio no Brasil (2014-2018) em informações claras para apoiar as ações de prevenção da Atenção Primária à Saúde (APS).

A análise busca fornecer um mapa do problema, permitindo que as equipes de saúde possam:

* Identificar os grupos de maior risco (por idade, sexo, raça);
* Descobrir se há meses ou épocas do ano com mais ocorrências;
* Focar em recursos, como equipes e campanhas, onde o impacto será maior.

### 💡 Perguntas norteadoras do projeto
**1. Existe diferença na taxa de suicídio entre os sexos (masculino e feminino)?**

**2. Há variação na incidência de suicídio relacionada à cor/raça?**

**3. Qual a distribuição de casos por faixa etária, e quais são as idades ou grupos etários de maior frequência?**

**4. Há evidências de sazonalidade? Existe algum mês ou período específico do ano que registra uma frequência ou quantidade mais alta de casos?**

* ADICIONAR MAIS PERGUNTAS

## 5. Ferramentas e Tecnologias
* Looker Studio
* BigQuery
* Python
* Google Colab

## 6. Fonte de Dados
* [Dataset | Dados de Suicídio no Brasil 2014 a 2018 (Kaggle)](https://www.kaggle.com/datasets/psicodata/dados-de-suicdio-no-brasil-2014-a-2018/data)
  
Período dos dados: 2014 a 2018

## 7. Como rodar o projeto

## 8. Estrutura do Repositório

### Pré-processamento de dados:
Descreva como os dados foram obtidos e qualquer processo de limpeza ou transformação realizado.
* Coleta e Ingestão: Selecionaram datasets, integraram múltiplas fontes no BigQuery
* Limpeza e Transformação: Trataram dados, criaram variáveis derivadas
* Análise Exploratória: Descobriram padrões, formularam hipóteses

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
  
## Referências
* [Notícia G1 | Brasil tem uma tentativa de suicídio ou autolesão entre adolescentes a cada 10 minutos](https://g1.globo.com/saude/saude-mental/noticia/2025/09/22/brasil-tem-uma-tentativa-de-suicidio-ou-autolesao-entre-adolescentes-a-cada-10-minutos.ghtml) 
