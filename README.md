# Previsão de Preço

Esse `README` expõe processo de criação de um modelo de ML utilizando a ferramenta no code Amazon Sagemaker Canvas, utilizando o dataset `Housing` localizado na pasta datasets desse mesmo repositório.

# Análise do Dataset e Construção do Modelo

Antes de partir para a criação do modelo em si, foi feita uma rápida análise do dataset, nessa análise foi constadado que não havia valores faltando, que o melhor tipo de modelo seria o **Numeric model type** e que há uma grande quantidade de variáveis categóricas binárias. Partindo para a construção a métrica escolhida para prever os coeficientes foi MSE, o dataset foi divido em sets de treinamento (80%) e validação (20%), o algoritimo de treinamento ficou a cargo do Amazon Sagemaker Canvas e o *target* escolhido foi a coluna **price**.

# Análise dos Resultados do Modelo

A princípo olhando as métricas **RMSE** e **MSE** podemos ter uma falsa noção de que o modelo performou mal, já que os valores foram respectivamente **1013091.25** e **1026353856512.000**, no entanto isso se deve fato de que os valores do target serem bastante elevados. Como o objetivo desse projeto era testar a capacidade do Amazon Sagemaker Canvas nenhum dado foi **Normalizado** ou **Padronizado** anteriormente, no entanto mesmo não realizando esses processos podemos ter uma melhor compreensão da performance do modelo olhando para a unidade de medida **R-squared** que apresentou um valor incrível de **70.641%**, isso signifca que as *features* do modelo conseguem explicar pelo menos 70% da variação no preço, sendo a que mais impactante a coluna **area**, como mostra a imagem a seguir:

![image](assets\area_grafico.png)

# Predições

Utilizando a ferramenta **single prediction** podemos comprovar que realmente a coluna de **area** é a que mais impacta na variação do preço.
![image](assets\impacto.png)