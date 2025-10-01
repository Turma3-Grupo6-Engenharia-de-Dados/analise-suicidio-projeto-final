# Escolha do dataset
- Escolhemos o dataset que reúne casos de suicídio no Brasil no período de 2014 a 2018;
- Apesar dos dados não serem os mais atuais possíveis, verificamos que a base de dados estava bem completa e continha variáveis interessantes para a nossa análise e que podiam trazer insights importantes que correspondem aos nossos objetivos;
- Não encontramos datasets tão completos quanto esse e que fossem mais recentes, considerando nossos temas de interesse para o projeto;

# Limpeza e transformação
- Removi as colunas que continham dados que não são relevantes para a nossa análise no momento;
- Removi as colunas que continham os dados de data de óbito (DTOBITO) e de data de nascimento (DTNASC) porque o df já possui uma coluna com os dados da idade (idade), que são relevantes para a análise atual;
- Apesar das informações de escolaridade e de ocupação serem interessantes para a análise atual, optei por remover as colunas (ESC e OCUP) por possuir muitos campos sem informação;
- Para garantir que o df vai conter apenas casos de suicídio, removi as linhas que tivessem o campo da circunstância do óbito (CIRCOBITO) preenchidos com uma causa diferente de 'suicídio';
- Como agora todos os dados estão relacionados a causa suicídio, a coluna CIRCOBITO não é mais necessária, portanto optei por removê-la;
- Com df.min() e df.max() foi possível observar que a base reúne casos de suicídio de pessoas de 0 a 113 anos.

# Análise exploratória 
A partir da análise realizada, contatou-se haver determinados padrões:
- A maioria dos casos são com Homens, cerca de 270% acima;
- Há diferenças de idades entre os homens e mulheres;
- Há uma maior ocorrência de casos em determinados meses do ano;

A partir da análise, formulou-se as seguintes hipóteses:
- H1 - Há um maior número de casos entre adolescentes (12 a 18 anos);
- H2 - O número de casos apresenta um padrão sazonal, variando de acordo com o mês do ano, ou seja, datas comemorativas tedem ter maior número de ocorrências;
- H3 - A distribuição de idade é diferente entre os grupos do sexo masculino e feminino, ainda que a mediana entre elas seja proxima.

