# Análise de Dados: Casos de Suicídio no Brasil 🎗️

## 1. Documentação 
* [Dashboard](https://lookerstudio.google.com/reporting/babf883d-9361-44b2-ad60-8e4b6103914b)
* [Apresentação](https://www.google.com.br) - pendente o link correto

## 2. Contexto do problema de negócio 

O suicídio representa um grave e complexo **desafio de saúde pública** no Brasil. Neste cenário, a Atenção Primária à Saúde (APS), como a principal porta de entrada do Sistema Único de Saúde (SUS) e o ponto de contato mais próximo da comunidade, desempenha um **papel fundamental na prevenção**.

A nossa consultoria, **Faster**, foi contratada para atender a uma demanda estratégica da área de saúde mental da APS. Com a aproximação do **Setembro Amarelo** (mês dedicado à prevenção do suicídio), a área de negócio identificou uma lacuna:
* As campanhas de prevenção são, frequentemente, genéricas e não direcionadas aos grupos de maior risco ou às épocas de maior ocorrência de casos.
  
Nesse sentido, a **equipe de dados** da consultoria Faster foi acionada para fornecer uma **visão analítica e detalhada** sobre a distribuição, os padrões e os fatores associados aos casos de suicídio no Brasil.

Este projeto de análise de dados visa nortear o planejamento estratégico das ações de prevenção ao suicídio e promoção da saúde mental da APS. A análise garantirá que os recursos sejam aplicados de forma eficaz e direcionada, maximizando o impacto da APS onde a necessidade é maior.

## 3. Objetivo 

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

## 4. Metodologia
* Escolhemos o dataset que reúne casos de suicídio no Brasil no período de 2014 a 2022;
* Apesar dos dados não serem os mais atuais, verificamos que a base de dados estava bem completa e continha variáveis interessantes para a nossa análise e que podiam trazer insights importantes que correspondem aos nossos objetivos.

## 5. Ferramentas e Tecnologias 
* Looker Studio
* BigQuery
* Python
* Google Colab
* Canva

## 6. Fonte de Dados 
* [Databases | SIM - Sistema de Informação sobre Mortalidade (PySUS)](https://pysus.readthedocs.io/pt/latest/databases/SIM.html)
* [Dataset | SIM - Sistema de Informação sobre Mortalidade (BigQuery)](https://console.cloud.google.com/bigquery?inv=1&invt=Ab4K-w&project=t1engenhariadados&ws=!1m4!1m3!3m2!1st1engenhariadados!2sGrupo_3_6_ProjetoFinal)
* Período: 2014 a 2022

## 7. Como rodar o projeto
* pendente*
  
## 8. Estrutura do Repositório
* pendente*

## 9. Pré-processamento de dados:

### **Ingestão e Preparação de Dados** 
O código e os resultados vêm de um projeto de ETL (Extract, Transform, Load) focado na ingestão e preparação de dados de mortalidade do Sistema de Informação sobre Mortalidade (SIM), disponibilizados pelo DATASUS
O objetivo é criar um conjunto de dados unificado, limpo e pronto para análise, abrangendo o período de 2014 a 2022.

O projeto utiliza a **biblioteca PySUS** para automatizar o download e processamento dos dados do DATASUS. O *fluxo de trabalho* principal está dividido em duas etapas:

**▫️Ingestão e Filtragem Anual** 
* O script baixa os dados de óbitos para cada ano, de 2014 a 2022, para todos os estados brasileiros;
* Em seguida, ele seleciona apenas as colunas essenciais para a análise (ESTADO, ANO, TIPOBITO, IDADE, SEXO, RACACOR, ESTCIV, ESC2010, LOCOCOR, CAUSABAS, e CIRCOBITO) e salva cada ano em um arquivo CSV separado.

**▫️Unificação e Limpeza Final** 
* Na etapa final, todos os arquivos CSV anuais são lidos e combinados em um único DataFrame. Este DataFrame unificado passa por uma limpeza rigorosa, onde são aplicados filtros específicos para casos de interesse, e a coluna de idade é transformada para um formato numérico consistente;
* O resultado é um arquivo CSV final que foi carregado ao banco de dados BigQuery e que pode ser usado para análise de dados.

### Análise Exploratória
▫️Com base nas perguntas norteadoras do projeto e em pesquisas sobre o tema, formulamos as seguintes hipóteses para guiar a análise exploratória dos dados:
* H1: Gênero e Suicídio: A taxa de suicídio é significativamente maior entre homens do que entre mulheres no Brasil, refletindo o "paradoxo de gênero" no comportamento suicida, onde homens tendem a usar métodos mais letais.
* H2: Raça/Cor e Suicídio: A incidência de suicídio varia entre diferentes grupos raciais, com taxas desproporcionalmente altas entre as populações branca e parda, mas também com variações importantes que podem indicar disparidades sociais e de acesso à saúde mental.
* H3: Faixa Etária e Suicídio: Existe uma concentração de casos de suicídio em faixas etárias específicas, particularmente entre jovens adultos (20-39 anos), mas com um aumento preocupante também em idades mais avançadas, sugerindo diferentes fatores de risco ao longo do ciclo de vida.
* H4: Sazonalidade: Os casos de suicídio apresentam um padrão de sazonalidade, com um número maior de ocorrências em determinados meses do ano, o que pode estar associado a fatores climáticos, sociais ou culturais.

### Modelagem Estatística

**Regressão de Poisson**

▫️A regressão de Poisson nos ajuda a entender o impacto de cada variável no número esperado de casos de suicídio, mantendo as outras variáveis constantes. O "Fator Multiplicativo" (ou Razão de Taxa de Incidência - IRR) nos diz o quanto a contagem de suicídios é multiplicada para cada categoria, em comparação com uma categoria de referência.
* Linha de Referência (vermelha em x=1): Se um ponto e seu intervalo de confiança estão à direita desta linha, a categoria tem um número esperado de casos maior do que a referência. Se estiver à esquerda, o número esperado é menor. Se o intervalo de confiança cruza a linha, a diferença pode não ser estatisticamente significativa.

<div align="center">
  <img src="https://scontent.fcgh2-1.fna.fbcdn.net/v/t39.30808-6/558341155_24562451400115324_4660526727345443347_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=127cfc&_nc_ohc=d2eDHIvJIlIQ7kNvwF8YiwU&_nc_oc=AdkRG1BuV0pfpx45Q9decpd30Na4_RGbPg8q3CTJHvdJ_dckjNcXjZSXgach2gWezw0Z0lkbjDJIFfxBPmcnjCiE&_nc_zt=23&_nc_ht=scontent.fcgh2-1.fna&_nc_gid=-EpH7kWGeXRrCzVC7ZZMag&oh=00_AfbEZO63FvYAuNMgiy4Gleu_eaGqpU7Zz2sErlzbfgxduw&oe=68E4AAD6" alt="Impacto de Ano no Número de Casos vs. Categoria de Referência">
</div>
<div align="center">
  <img src="https://scontent.fcgh2-1.fna.fbcdn.net/v/t39.30808-6/557603107_24562451403448657_1327562664930644781_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=127cfc&_nc_ohc=ZgwUPGVykFQQ7kNvwEXCDFZ&_nc_oc=AdmZ_gqFw0cdFN6BdzpzqZmS6Nbml9JIiYpAt3kfL8ZlU6dOL8mbqYxZ2cxTC0sLxMW5JiJ0IMbNKUq0oXqrhnGd&_nc_zt=23&_nc_ht=scontent.fcgh2-1.fna&_nc_gid=DyyAJy5efBBCr9v4HHxGQg&oh=00_AfbQJeUqbf8arR9Ol51WgLEX8p8sUKbYjcd3LTGYJOzlGQ&oe=68E49F1C" alt="Impacto de Faixa Etária no Número de Casos vs. Categoria de Referência">
</div>
<div align="center">
  <img src="https://scontent.fcgh2-1.fna.fbcdn.net/v/t39.30808-6/556676717_24562451406781990_6586301673927646430_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=127cfc&_nc_ohc=e4hHy0t0VlkQ7kNvwFR6SL2&_nc_oc=Adk4xehG8ZqJdJVMxqyScUIkgENzPQhArsVfrtCYmaG78VvQVF6Vc8UA3FS_pstMWMkGjFDMXAsXwzy8wh99Ni0m&_nc_zt=23&_nc_ht=scontent.fcgh2-1.fna&_nc_gid=oYkq93xv4xnmMV0y-QYczQ&oh=00_AfYph9M0k6I_reaLN8sVEBk5bDsglO8SgNKTgE87upenpg&oe=68E48EDD" alt="Impacto de Raça/Cor no Número de Casos vs. Categoria de Referência">
</div>

▫️ Principais insights do Modelo
1. **Ano:** O gráfico mostra um **aumento progressivo** no fator multiplicativo ao longo dos anos, em comparação com o ano de referência (2014). Isso confirma a tendência de crescimento no número de casos que já havíamos observado na análise exploratória. Por exemplo, o ano de 2022 tem um fator multiplicativo significativamente maior que 1, indicando um aumento no número de casos em relação a 2014, mesmo controlando por outras variáveis.
2. **Sexo:** O fator multiplicativo para o sexo **Masculino ('M')** é substancialmente maior que 1, em comparação com o sexo Feminino (referência). Isso significa que, mesmo controlando por ano, raça e faixa etária, o número esperado de suicídios para homens é várias vezes maior do que para mulheres. Este é um dos fatores com maior poder explicativo no modelo.
3. **Raça/Cor:** Comparando com a raça/cor de referência (branca), observamos que os fatores multiplicativos para as outras categorias (parda, preta, indígena) são **menores que 1**. Isso sugere que, controlando pelas outras variáveis, esses grupos têm um número esperado de casos menor do que o grupo de referência (brancos). **Novamente, é crucial lembrar que esta é uma análise de contagem, não de taxas**. A população branca é maior no Brasil, o que influencia a contagem. O resultado do modelo aqui reflete a contagem absoluta de casos, não o risco por habitante.
4. **Faixa Etária:** O gráfico mostra que, em comparação com a faixa de 0-9 anos (referência), todas as outras faixas etárias têm um fator multiplicativo **extremamente elevado**. Os picos ocorrem nas faixas de **20-29 e 30-39 anos**, confirmando que essas são as idades com a maior contagem esperada de casos. Após os 40 anos, o fator começa a diminuir, mas permanece muito acima da linha de referência até as idades mais avançadas.

## 10. Conclusões 

### 💡Insights
*	A distribuição por sexo revela uma **disparidade significativa**, **com 78,4%** dos casos de suicídio no período analisado ocorrendo entre homens. Este é um padrão **consistente em todo o Brasil** e está alinhado com o "paradoxo de gênero no suicídio".
*	A proporção entre os sexos **varia regionalmente**, por exemplo, de **26,7%** de casos femininos no **Rio de Janeiro (RJ)** para **17,8%** na Bahia **(BA)**, sugerindo que fatores regionais e culturais influenciam essa disparidade.
*	Há uma **tendência de aumento no número de casos** para ambos os sexos na maioria dos estados ao longo do período de 2014 a 2018 (e continua até 2022).
*	A maioria dos casos de suicídio ocorre em números absolutos entre pessoas **brancas (50,2%) e pardas (43,0%)**.
*	A **tendência de crescimento** nos casos de suicídio é observada **para todos os grupos raciais**, sendo mais pronunciada nas populações branca e parda, mas consistente também para a população preta e indígena.
*	A análise cruzada mostra que a disparidade de gênero se mantém em todos os grupos raciais, mas a proporção de casos masculinos é um pouco maior nas populações **parda (80,5%)** e **preta (81,4%)** em comparação com a **branca (76,4%)**. Isso sugere **dupla vulnerabilidade**.
*	O suicídio afeta todas as idades, mas há uma **concentração alarmante entre os jovens adultos**. As faixas etárias de **20-29 anos e 30-39 anos** somam juntas mais de **41%** do total de casos.
*	Há um novo, embora menor, **pico de preocupação entre os idosos (70+)**.

### 🟡 Recomendações práticas baseadas nos insights
Com base nas discussões dos resultados, temos as seguintes recomendações:

*	As campanhas de prevenção ao suicídio devem ter uma **comunicação direcionada e sensível às questões de masculinidade e saúde mental masculina**.
*	É essencial **desmistificar a ideia de que procurar ajuda é um sinal de fraqueza**.
*	**Estratégias de abordagem** na Atenção Primária podem ser desenvolvidas para **identificar sinais de sofrimento psíquico em homens durante consultas de rotina**, mesmo que a queixa principal não seja relacionada à saúde mental.
*	As estratégias de prevenção devem ser **adaptadas às realidades locais**. Em estados com uma disparidade de gênero ainda maior, as ações focadas no público masculino podem ser ainda mais prioritárias.
*	O **monitoramento contínuo** desses dados é fundamental. A APS pode usar o dashboard desenvolvido para acompanhar a tendência em sua região e **responder rapidamente a aumentos inesperados no número de casos**.
*	As campanhas devem ser **culturalmente sensíveis** e considerar as especificidades de cada grupo racial.
*	A Atenção Primária pode estar atenta a **fatores de risco que afetam desproporcionalmente certos grupos**, como o racismo estrutural, a discriminação e as desigualdades socioeconômicas.
*	A APS em territórios com maior presença de populações específicas (como áreas com grande população indígena ou quilombola) deve estar preparada para **oferecer um cuidado culturalmente adequado** e atento às tendências de crescimento de casos nesses grupos.
*	As estratégias de prevenção para homens devem ser ainda mais **interseccionais**, considerando como a raça e a classe social interagem com as questões de gênero.
*	As campanhas de prevenção devem ter um **foco prioritário no público jovem (20 a 39 anos)**, utilizando canais de comunicação e linguagem adequados a essa população.
*	Para os idosos, a **integração do cuidado em saúde mental com o tratamento de doenças crônicas e o combate ao isolamento social** é fundamental.

### 📊 Impacto esperado para o negócio 
O impacto principal é a transformação de campanhas genéricas em ações estratégicas, resultando em:
*	**Otimização de recursos:** Ao focar as ações como recursos, equipes e campanhas nos grupos de maior risco (homens e jovens adultos) e nas regiões de maior vulnerabilidade, a APS **maximiza o retorno do investimento** e a efetividade das intervenções.
*	**Melhoria na qualidade da intervenção:** Os profissionais da APS estarão **mais bem preparados** para oferecer um cuidado **mais eficaz e equitativo**, cientes das múltiplas camadas de vulnerabilidade (gênero, raça/cor e idade).
*	**Resposta proativa:** O monitoramento contínuo dos dados permite que a APS **antecipe tendências e responda rapidamente a picos de casos**, fortalecendo as políticas de saúde mental e a prevenção em todo o país.

### 🎯Como a solução pode ser aplicada? 
A solução da Faster fornece as seguintes ferramentas e o conhecimento estratégico necessários para a implementação ações recomendadas:
*	**Direcionamento da comunicação:** Os insights fornecidos (ex: foco na masculinidade, linguagem para jovens) são o **novo briefing** para as campanhas de Setembro Amarelo e anuais.
*	**Revisão de protocolos:** As recomendações (ex: triagem de saúde mental em consultas de rotina masculinas) devem ser **integradas aos protocolos de atendimento da APS**.
*	**Ferramenta de Monitoramento:** A APS pode usar o dashboard desenvolvido da consultoria para acompanhar a tendência em sua região e responder rapidamente a aumentos inesperados no número de casos.
*	**Base para Análises Futuras:** A análise comparativa entre estados e a necessidade de calcular as taxas de suicídio por 100 mil habitantes são o ponto de partida para investigações futuras mais aprofundadas sobre fatores contextuais (crises econômicas, desastres, etc).

## 11. Limitações 
* O principal desafio que enfrentamos foi no começo, tínhamos um período de análise menor (2014 a 2018), mas trabalhando em equipe conseguimos estender o período para 2014 a 2022, o que nos deu uma visão muito mais robusta em relação aos dados.
* O tempo de desenvolvimento do projeto também foi outro desafio, nos alinhamos e priorizamos as etapas para garantir a entrega, o que nos ensinou muito sobre planejamento e organização.
* A principal limitação que encontramos foi que os dados mais atuais (2023 e 2024) ainda não estavam disponíveis ou consolidados nas bases do DATASUS. Por isso, a análise se baseou em dados históricos até 2022. 
* Aprendemos que **saber por onde começar e priorizar as perguntas norteadoras do projeto** foi essencial e nos ajudou muito. Isso facilitou o desenvolvimento das próximas etapas e do próprio dashboard, garantindo que todo o trabalho estivesse alinhado aos objetivos da APS.
* Para os próximos passos, queremos obter as bases de dados mais atuais (2023, 2024 e 2025) assim que estiverem disponíveis e integrá-las ao nosso dashboard. Isso é fundamental para a APS ter uma visão em tempo quase real das tendências.

## 12. 👥 Equipe
* Caroline Cortez
* Carlos Ryan
* Emerson Oliveira
* Gisely Karla
* Laila Guedes
* Nathalia Kopke
* Vaneza Magalhães
  
## 🔗 13. Referências
* [Notícia G1 | Brasil tem uma tentativa de suicídio ou autolesão entre adolescentes a cada 10 minutos](https://g1.globo.com/saude/saude-mental/noticia/2025/09/22/brasil-tem-uma-tentativa-de-suicidio-ou-autolesao-entre-adolescentes-a-cada-10-minutos.ghtml)
* [OPAS | Atenção Primária à Saúde](https://www.paho.org/pt/topicos/atencao-primaria-saude)
* [PySUS | Base de Dados - Sistema de Informação sobre Mortalidade (SIM)](https://pysus.readthedocs.io/pt/latest/index.html)
