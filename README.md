

# Projeto de PI3 - Análise de sentimentos em reviews de produtos 

Carolina de Farias

Orientadores: Daniel Lohmann e Robinson Pizzio.

# Sobre o projeto
O objetivo desse trabalho é obter quais são os sentimentos dos consumidores em relação a um produto frente a uma classificação negativa, portanto, pretende-se extrair quais são os fatores citados quando uma avaliação de um produto é baixa, afim de oferecer essa solução para o fabricante. 

Assim, é possível identificar quais são os problemas em relação a um produto, possibilitando agilizar o processo de melhorias.

# O que é análise de sentimentos? 
Análise de sentimento é o campo de estudo que analisa opiniões, sentimentos, atitudes e emoções de pessoas relacionados a produtos, serviços, organizações, indivíduos, problemas ou eventos. Atualmente, na internet, existe uma grande quantidade de opiniões sobre um produto, o que pode ajudar o consumidor na tomada de decisões e também as empresas, já que através dessas avaliações é possível encontrar quais são os pontos positivos e negativos sobre um produto.

O  objetivo da análise de sentimento é extrair o real  significado de um texto sem isso ter de ser feito manualmente. Para que a análise de sentimento seja efetiva, um dos  maiores pilares é o aprendizado de máquina, do qual é utilizado  para reconhecer padrões e predizer resultados.

# Requisitos técnicos para rodar o projeto

Esse projeto foi desenvolvido em Python utilizando o Jupyter, para rodar esse projeto, basta executar o arquivo "analise_de_reviews_de_produtos.ypnb" e fazer o upload das bases de dados disponíveis na pasta "base de dados", carregando os arquivos ".csv" disponíveis.

# Base de dados utilizada para treinamento
Foi utilizada uma base de dados já coletada para realizar o treinamento, disponibilizada pela Olist através do site do kaggle, em que o link pode ser encontrado abaixo. Além disso, para validar os resultados, criou-se uma nova base de dados com reviews sobre o produto Iphone, disponibilizados na web pelo site da Casas Bahia.

Base disponível em:
https://www.kaggle.com/olistbr/brazilian-ecommerce

# Fluxo para a análise de dados
Nesse trabalho, foi obedecido o seguinte fluxo

![img](https://lh5.googleusercontent.com/N8bp88rL0i8dYL-u1CNFtSjmpsh2ZPcyFJkYaRdTZWTFIR23ly57SGd9YsYMe-68EueqXyyBq8jsTapOmlHv1kWTN3LOjec9TxiWDaTKilBb12Afj96RWqkz_4Ok3O5QQ4v17RilkdOI)



#  Sobre a base de dados

Em nossa base, temos o seguinte cenário.

| Classificação                     | Tamanho |
| --------------------------------- | ------- |
| Tamanho total dos dados           | 99224   |
| Total de classificações positivas | 76470   |
| Total de classificações negativas | 14575   |
| Total de classificações neutras   | 8179    |

Além disso, ao gerar a wordCloud, é possível ter uma noção de quais são as palavras mais utilizadas.

![img](https://lh6.googleusercontent.com/7DU3comYY5KWdOwF35LwziR-RYt0CJQBddBVg8wG8ezCgTN7RTklZcRthzI5YN31taAjliPrmP4MD31PrCuhFbSYeg8GQHd77glUcahPHqJZts-b5_ThgmBSrTsYmtE1wbGJ9MBI-h-B)

# Pré-processamento dos dados

Foram aplicadas as seguintes técnicas no pré-processamento dos dados.

1. Definição das colunas de interesse da base.

2. Definição dos scores conforme positivo ou negativo.

3. Retirada das linhas em branco, ou seja, aquelas que continham score, mas não continham nenhum comentário sobre o produto.

4. Filtro para tentar obter somente as avaliações que se refiram ao produto, sem deixar de utilizar aquelas que se referem ao produto e a entrega/loja.

5. Modelagem da base de dados conforme das técnicas de processamento.

   Assim, após o pré-processamento dos dados, temos o seguinte contexto na base de dados:

   | Classificação                                           | Total |
   | ------------------------------------------------------- | ----- |
   | Total de classificações negativas(entre 0 e 3 estrelas) | 10660 |
   | Total de classificações positivas(entre 4 e 5 estrelas) | 16951 |

# Aprendizado supervisionado e Processamento de Linguagem Natural (NLP)

O framework NLTK (Natural Language Tool Kit) da  linguagem de programação Python foi utilizado para a  aplicação de algoritmos, treinamento e predição de dados,  podendo comparar os resultados dos diversos algoritmos. Assim, nesse projeto, é utilizado o aprendizado de máquina supervisionado.

| Algoritmo             | Acurácia |
| --------------------- | -------- |
| Bernoulli Naive bayes | 84,72%   |
| Naive Bayes           | 82.54%   |
| Linear SVC            | 84,30%   |
| Regressão Logística   | 86,62%   |

Como o algoritmo de Regressão Logística apresentou melhor resultado, ele foi utilizado para realizar a obtenção do resultado final.

No gráfico abaixo, é possível observar a frequência das palavras positivas mais utilizadas.

![img](https://lh3.googleusercontent.com/9a2Rv8iuTBVYsBz0htO1CNVDeuDsTrzRLZADuapMCgAbK4QBsL862vS5JKZMfiPZaHvdCsLPfQaJSnlGBRRqHQSAgr3FLsj8gPb987hFO3OjjPYq6vIZk7EVdARdEQXk6ISFLjzS_NNA)

Abaixo, temos a frequência das palavras negativas mais utilizadas.

![img](https://lh5.googleusercontent.com/5-UbKbMrggC-sHVsq5frXxlLxPIlzzn0Jvb7TI3aV2z3U9GjXPNc6f6C_Om68-x0a2QmCpwCsNhu_Jgf6ousr0mp7wnn0eNdwT-3_2lzAVyzeEaCXWisOM0X2riF6K7zFo_loa4FgLm9)

# Validação de resultados

Para a validação final, foi feito uma nova base com 100 comentários sobre um telefone celular disponível em um e-commerce, assim, é possível observar através da Word Cloud que as palavras mais citadas negativamente sobre o produto são:

1. Carregador.
2. Fone de ouvido.
3. Bateria.
4. Preço.
5. Câmera.
6. Display.

![img](https://lh4.googleusercontent.com/rwSTWKorFPD2mxxIQSusAlsuTwEqa7tfbGoQdl1lAHcrJMwnlggsQRMaqB_A1E4opzz4F0RzCMEX8_dCfKH58utbqa5jWj_F_RFsJWApY330FrgqhE9vX15txaUTRhHPGARbJgYIhxtr)

# Referências

[1] L. Bing, Sentiment Analysis and Opinion Mining, vol. 5, no. 1. 2012.

[2 ] R. L. de S. Santos and R. S. Moura, “Extração de Métricas e  Análise de Sentimentos em Comentários Web do Domínio de Hotéis,”  Corpus, 2010.

[3]  X. Fang and J. Zhan, “Sentiment analysis using product review  data,” J. Big Data, vol. 2, no. 1, 2015.

[4]  S. Bird, E. Klein, and E. Loper, Natural Language Processing with  Python, vol. 1. O’Reilly Media, 2009.
