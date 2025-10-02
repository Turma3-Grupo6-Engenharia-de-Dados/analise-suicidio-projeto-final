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
* Escolhemos o dataset que reúne casos de suicídio no Brasil no período de 2014 a 2022
* Apesar dos dados não serem os mais atuais possíveis, verificamos que a base de dados estava bem completa e continha variáveis interessantes para a nossa análise e que podiam trazer insights importantes que correspondem aos nossos objetivos

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

### **Ingestão e Preparação de Dados de Mortalidade no Brasil (2014-2022)** ✅
O código e os resultados vêm de um projeto de ETL (Extract, Transform, Load) focado na ingestão e preparação de dados de mortalidade do Sistema de Informação sobre Mortalidade (SIM), disponibilizados pelo DATASUS
O objetivo é criar um conjunto de dados unificado, limpo e pronto para análise, abrangendo o período de 2014 a 2022.

O projeto utiliza a **biblioteca PySUS** para automatizar o download e processamento dos dados do DATASUS. O *fluxo de trabalho* principal está dividido em duas etapas:

**▫️Ingestão e Filtragem Anual:** ✅
* O script baixa os dados de óbitos para cada ano, de 2014 a 2022, para todos os estados brasileiros
* Em seguida, ele seleciona apenas as colunas essenciais para a análise (ESTADO, ANO, TIPOBITO, IDADE, SEXO, RACACOR, ESTCIV, ESC2010, LOCOCOR, CAUSABAS, e CIRCOBITO) e salva cada ano em um arquivo CSV separado

**▫️Unificação e Limpeza Final:** ✅
* Na etapa final, todos os arquivos CSV anuais são lidos e combinados em um único DataFrame. Este DataFrame unificado passa por uma limpeza rigorosa, onde são aplicados filtros específicos para casos de interesse, e a coluna de idade é transformada para um formato numérico consistente
* O resultado é um arquivo CSV final que foi carregado no banco de dados BigQuery ou pode ser usado para análise de dados

### Análise Exploratória
▫️Com base nas perguntas norteadoras do projeto e em pesquisas sobre o tema, formulamos as seguintes hipóteses para guiar a análise exploratória dos dados:
* H1: Gênero e Suicídio: A taxa de suicídio é significativamente maior entre homens do que entre mulheres no Brasil, refletindo o "paradoxo de gênero" no comportamento suicida, onde homens tendem a usar métodos mais letais.
* H2: Raça/Cor e Suicídio: A incidência de suicídio varia entre diferentes grupos raciais, com taxas desproporcionalmente altas entre as populações branca e parda, mas também com variações importantes que podem indicar disparidades sociais e de acesso à saúde mental.
* H3: Faixa Etária e Suicídio: Existe uma concentração de casos de suicídio em faixas etárias específicas, particularmente entre jovens adultos (20-39 anos), mas com um aumento preocupante também em idades mais avançadas, sugerindo diferentes fatores de risco ao longo do ciclo de vida.
* H4: Sazonalidade: Os casos de suicídio apresentam um padrão de sazonalidade, com um número maior de ocorrências em determinados meses do ano, o que pode estar associado a fatores climáticos, sociais ou culturais.

### Modelagem Estatística

**Regressão de Poisson**

▫️A regressão de Poisson nos ajuda a entender o impacto de cada variável no número esperado de casos de suicídio, mantendo as outras variáveis constantes. O "Fator Multiplicativo" (ou Razão de Taxa de Incidência - IRR) nos diz o quanto a contagem de suicídios é multiplicada para cada categoria, em comparação com uma categoria de referência
![This is an alt text.](https://scontent.fcgh2-1.fna.fbcdn.net/v/t39.30808-6/557590670_24562412516785879_5163892656830606304_n.jpg?_nc_cat=102&ccb=1-7&_nc_sid=127cfc&_nc_ohc=BPXpBX7IaWkQ7kNvwGwL7fd&_nc_oc=AdmQ4mwlbD2jgwaBmKSkFhQQUiv5slGoMbJq9nnlGOiS0AkOC788e4NU0aOusFu9_oK7NMpeN9-coKqALPssQQdy&_nc_zt=23&_nc_ht=scontent.fcgh2-1.fna&_nc_gid=SDvdjudQ3ncLSokdTFe1kQ&oh=00_Afa7u29sGfTkkN9H9c3uks40oqBEQP84Bk6CY-LEq7biBw&oe=68E4946A "Impacto de Ano no Número de Casos vs. Categoria de Referência")
![This is an alt text.](https://scontent.fcgh2-1.fna.fbcdn.net/v/t39.30808-6/557594104_24562399023453895_5117370097060960052_n.jpg?_nc_cat=101&ccb=1-7&_nc_sid=127cfc&_nc_ohc=5vEKnq_G98EQ7kNvwF_XUkM&_nc_oc=AdmKR7QgY61RFwi49Koh178AxUiTKT2MJPFuv_DfZMEMRdU2f_iA2rgacnVeIc-7cTEHrp2iDlfiHOC_5sdv9ImH&_nc_zt=23&_nc_ht=scontent.fcgh2-1.fna&_nc_gid=QD0bJVcpIKVJmBIWROCd7A&oh=00_AfYEwtfSX2DfSYBm-wj3umGswSh-sxn_IwQFtB1g3gFMQA&oe=68E4AC73 "Impacto de Faixa Etária no Número de Casos vs. Categoria de Referência")
![This is an alt text.](https://scontent.fcgh2-1.fna.fbcdn.net/v/t39.30808-6/557629462_24562403193453478_7134744093296190557_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=127cfc&_nc_ohc=kQJ1ZBnPA8AQ7kNvwHyuvNo&_nc_oc=AdmdQNND0k8XvRyaTMSMoHAIxgXrrFoYNb4_tOkbq54kPy1bUUF4JegWQ_EC41qptJvmxabqo9BHZ5sHysXm4VgH&_nc_zt=23&_nc_ht=scontent.fcgh2-1.fna&_nc_gid=NywZ5S0lqbzGuK_EE3K6rg&oh=00_AfZ8rAB8CysYyDRcfqjxinzIFx7M436Sl22CX_mH1-mjTQ&oe=68E4A8CD "Impacto de Raça/Cor no Número de Casos vs. Categoria de Referência")


* Linha de Referência (vermelha em x=1): Se um ponto e seu intervalo de confiança estão à direita desta linha, a categoria tem um número esperado de casos maior do que a referência. Se estiver à esquerda, o número esperado é menor. Se o intervalo de confiança cruza a linha, a diferença pode não ser estatisticamente significativa.


## 10. Conclusões 
Apresenta os principais resultados obtidos a partir da análise de dados. Sumariza as conclusões tiradas do projeto, incluindo insights importantes, descobertas relevantes e possíveis 
* Principais descobertas
* Insights 
* Recomendações práticas baseadas nos insights
* Impacto esperado para o negócio
* Como a solução pode ser aplicada
  
## 11. Limitações 
Identifique e descreva quaisquer limitações ou desafios encontrados durante o projeto. Sugira possíveis próximos passos para estender ou aprimorar o projeto de análise de dados.**
* Principais desafios enfrentados e como foram superados
* Principais limitações identificadas
* Lições aprendidas durante o projeto
  
## 🔗 12. Referências
* [Notícia G1 | Brasil tem uma tentativa de suicídio ou autolesão entre adolescentes a cada 10 minutos](https://g1.globo.com/saude/saude-mental/noticia/2025/09/22/brasil-tem-uma-tentativa-de-suicidio-ou-autolesao-entre-adolescentes-a-cada-10-minutos.ghtml)
* [OPAS | Atenção Primária à Saúde](https://www.paho.org/pt/topicos/atencao-primaria-saude)
* [PySUS | Base de Dados - Sistema de Informação sobre Mortalidade (SIM)](https://pysus.readthedocs.io/pt/latest/index.html)
