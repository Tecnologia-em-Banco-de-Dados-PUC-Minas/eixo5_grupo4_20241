## 4.2. Classificação de risco 

A base de dados não vem com classificação de risco prévia. Antes de treinarmos o modelo a classificar risco, precisamos estabelecer, portanto, a nossa definição de risco, e classificar nossa base de treinamento de acordo com tal. 

A classificação para treinamento será baseada nos acidentes que já aconteceram, assim, utilizamos os seguintes atributos: “parte do corpo afetada”, “natureza da lesão” e “Ocorrência de óbito”. Consultando o histórico de acidentes, podemos relacionar quais partes do corpo e tipos de lesão provocam mais óbitos e a partir desta referência atribuir uma nota de risco para cada registro. Dessa forma, conseguiremos treinar nosso modelo com base no que já aconteceu, para que ele nos forneça uma equação que preveja riscos futuros baseados em outros atributos que não dependam de fatos passados, como sexo, ocupação, idade, etc. 

Seguindo este raciocínio, a classificação da base de treinamento é feita, automaticamente, de acordo com o seguinte algorítmo: 

Para cada atributo (parte do corpo, natureza da lesão), ranquear seus valores por frequência (número de ocorrências na base), e representatividade percentual de óbitos na base (porcentagem de óbitos com relação ao total de óbitos da base). 

Uma nota é atribuída para cada faixa do ranking. Notas de 1 a 4 para frequência (maior nota para valores mais frequentes) e de 0 a 3 para representatividade de óbito (maior nota para valores com mais óbitos). 

A nota de risco para o atributo é obtida pela multiplicação das notas de faixa de ranking, divida por 12, para que os resultados fiquem entre 0 e 1. 

### Figura 2 – Esquema de ranqueamento e classificação de risco dos atributos relevantes 
![Esquema de ranqueamento e classificação de risco dos atributos relevantes](imagens/etapa4_img_classificacao1.png)
Fonte: Autores, 2024.

### Figura 3 – Exemplo de atributos classificados após o ranqueamento
![Exemplo de atributos classificados após o ranqueamento1](imagens/etapa4_img_classificacao2_1.png)
![Exemplo de atributos classificados após o ranqueamento2](imagens/etapa4_img_classificacao2_2.png)
Fonte: Autores, 2024.
