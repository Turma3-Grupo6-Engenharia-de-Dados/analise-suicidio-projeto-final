# Análise de Dados: Casos de Suicídio no Brasil 🎗️

## 1. 👥 Equipe ✅
* Caroline Cortez
* Carlos Ryan
* Emerson Oliveira
* Gisely Karla
* Laila Guedes
* Nathalia Kopke
* Vaneza Magalhães

## 2. Documentação 
* [Dashboard](https://lookerstudio.google.com/reporting/babf883d-9361-44b2-ad60-8e4b6103914b)
* [Apresentação](https://www.google.com.br) - pendente o link correto

## 3. Contexto do problema de negócio ✅

O suicídio representa um grave e complexo **desafio de saúde pública** no Brasil. Neste cenário, a Atenção Primária à Saúde (APS), como a principal porta de entrada do Sistema Único de Saúde (SUS) e o ponto de contato mais próximo da comunidade, desempenha um **papel fundamental na prevenção**.

Nossa consultoria, a **FAST**, foi contratada para atender a uma demanda estratégica da área de saúde mental da APS. Com a aproximação do **Setembro Amarelo** (mês dedicado à prevenção do suicídio), a área de negócio identificou uma lacuna:
* As campanhas de prevenção são, frequentemente, genéricas e não direcionadas aos grupos de maior risco ou às épocas de maior ocorrência de casos.
  
Nesse sentido, a **equipe de dados** da consultoria FAST foi acionada para fornecer uma **visão analítica e detalhada** sobre a distribuição, os padrões e os fatores associados aos casos de suicídio no Brasil.

Este projeto de análise de dados visa nortear o planejamento estratégico das ações de prevenção ao suicídio e promoção da saúde mental da APS. A análise garantirá que os recursos sejam aplicados de forma eficaz e direcionada, maximizando o impacto da APS onde a necessidade é maior.

## 4. Objetivo ✅

O objetivo deste projeto é transformar dados brutos sobre suicídio no Brasil (2014-2022) em insights para apoiar no planejamento das ações de prevenção da Atenção Primária à Saúde (APS).

A análise busca fornecer um mapeamento do problema, permitindo que as equipes de saúde possam:

* Identificar os grupos de maior risco (por idade, sexo, raça);
* Analisar a sazonalidade dos casos, descobrindo se há meses ou épocas do ano com maior ocorrência;
* Otimizar a alocação de recursos (equipes e campanhas), focando a intervenção onde o potencial de impacto é maior.

### 💡 Perguntas norteadoras do projeto
**1. Existe diferença na taxa de suicídio entre os sexos (masculino e feminino)?**

**2. Há variação na incidência de suicídio relacionada à cor/raça?**

**3. Qual a distribuição de casos por faixa etária, e quais são as idades ou grupos etários de maior frequência?**

**4. Há evidências de sazonalidade? Existe algum mês ou período específico do ano que registra uma frequência ou quantidade mais alta de casos?**

## Metodologia
* Dataset escolhido e justificativa - pendente

## 5. Ferramentas e Tecnologias ✅
* Looker Studio
* BigQuery
* Python
* Google Colab
* Canva

## 6. Fonte de Dados ✅
* [Databases | SIM - Sistema de Informação sobre Mortalidade (PySUS)](https://pysus.readthedocs.io/pt/latest/databases/SIM.html)
* [Dataset | SIM - Sistema de Informação sobre Mortalidade (BigQuery](https://console.cloud.google.com/bigquery?inv=1&invt=Ab4K-w&project=t1engenhariadados&ws=!1m4!1m3!3m2!1st1engenhariadados!2sGrupo_3_6_ProjetoFinal)
* Período: 2014 a 2022

## 7. Como rodar o projeto
* pendente*
  
## 8. Estrutura do Repositório
* pendente*

## 9. Pré-processamento de dados:
Descreva como os dados foram obtidos e qualquer processo de limpeza ou transformação realizado.
* Coleta e Ingestão: Selecionaram datasets, integraram múltiplas fontes no BigQuery
* Limpeza e Transformação: Trataram dados, criaram variáveis derivadas
* Análise Exploratória: Descobriram padrões, formularam hipóteses
* Modelagem Estatística: Testaram hipóteses, construíram modelos preditivos
---
* Criar uma View**: Construir views para simplificar análises futuras.

## 10. Métodos e técnicas:
* Documente as técnicas e metodologias usadas na análise.

## 11. Conclusões 
Apresenta os principais resultados obtidos a partir da análise de dados. Sumariza as conclusões tiradas do projeto, incluindo insights importantes, descobertas relevantes e possíveis 
* Principais descobertas
* Insights 
* Recomendações práticas baseadas nos insights
* Impacto esperado para o negócio
* Como a solução pode ser aplicada
  
## 12. Limitações 
Identifique e descreva quaisquer limitações ou desafios encontrados durante o projeto. Sugira possíveis próximos passos para estender ou aprimorar o projeto de análise de dados.**
* Principais desafios enfrentados e como foram superados
* Principais limitações identificadas
* Lições aprendidas durante o projeto
  
## 13. Referências
* [Notícia G1 | Brasil tem uma tentativa de suicídio ou autolesão entre adolescentes a cada 10 minutos](https://g1.globo.com/saude/saude-mental/noticia/2025/09/22/brasil-tem-uma-tentativa-de-suicidio-ou-autolesao-entre-adolescentes-a-cada-10-minutos.ghtml)
* [OPAS | Atenção Primária à Saúde](https://www.paho.org/pt/topicos/atencao-primaria-saude)
* [PySUS | Base de Dados - Sistema de Informação sobre Mortalidade (SIM)](https://pysus.readthedocs.io/pt/latest/index.html)
