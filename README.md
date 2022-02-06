# PI3

# Sobre o projeto
O objetivo desse trabalho é obter quais são os sentimentos em relação a um produto frente a uma classificação negativa, portanto, pretende-se extrair quais são os fatores citados quando uma avaliação de um produto é negativa, afim de oferecer essa solução para o fabricante.

# O que é análise de sentimentos? 
Análise de sentimentos ou mineração de opiniões refere-se ao uso de NLP (processamento de linguagem natural) cujo objetivo é identificar, extrair e quantificar a polaridade expressada nos dados.

# Qual a dificuldade em realizar esse trabalho?
Para o aprendizado da máquina, é difícil trabalhar com metáforas, ironias, brincadeiras. Além disso, é complexo também se trabalhar com muitos sentimentos em uma sentença, por exemplo:
          "Esse telefone é muito bonito, mas a bateria deixa a desejar".
Nessa sentença, é dificil para a máquina compreender se o objetivo desse usuário foi expressar uma sentença positiva ou negativa. Para esse trabalho, essa é uma sentença relevante, portanto, é um desafio compreender como agregar isso.

# Níveis na análise de sentimento
Existem 3 níveis de análise de sentimento: nível de documento completo, de sentença ou de aspecto. No nível de documento, todo o texto pode ser classificado como positivo, neutro ou negativo. No nível de sentença, o texto é dividido em sentenças, que têm suas polaridades calculadas individualmente. Já no nível de aspecto, são extraídos dos textos
várias entidades e aspectos, e depois é calculada a polaridade para cada um deles.
Nesse projeto **AINDA NÃO ESTÁ DEFINIDO QUAL NÍVEL SERÁ TRABALHADO**.
**JUSTIFICAR O PORQUE DA ESCOLHA DA SENTENÇA**.

# Tipos de abordagem
Existem diversas abordagens para realizar essa análise de dados, nesse trabalho, sera utilizado a machine learning, a grande vantagem de utilizar essa abordagem é que não há dependência de idiomas, diferente da abordagem do tipo léxico. A principal desvantagem desse modelo, é a necessidade de treinar os dados.

**Esclarecer melhor a abordagem**
**Porque não utilizar o deep learning?** Deep learning é um modelo que vêm crescendo muito, entretanto, uma das principais desvantagens é a necessidade de utilizar muitos dados para o treino, o que pode ser muito custoso, então, nesse primeiro momento, definiu-se a abordagem de machine learning.

# Fluxo de dados.
Primeiramente, é preciso realizar uma filtragem dos dados, pois podem ocorrer a existência de caracteres especiais ou emojis, que não podem ser considerados em nossa análise. Após isso, é necessário realizar a mineração desses dados, em que iremos buscar padrões e regras, afim de obter quais são os registros negativos e por fim, o pós processamento do dado, objetivando obter quais foram as palavras negativas mais utilizadas sobre o produto.

![image](https://user-images.githubusercontent.com/40871824/142950430-3d68db30-165e-4793-988c-db8e939b5661.png)

# Base de dados utilizada para treinamento.
Será utilizada uma base de dados já coletada para realizar o treinamento.

Base disponível em:
https://www.kaggle.com/olistbr/brazilian-ecommerce

# Plataforma de desenvolvimento.
Para esse trabalho, pretende-se utilizar o Google Colab, muito utilizado em abordagens de machine learning.

# Informações sobre a base de dados
Para compreender como os dados da base escolhida estão dispostos, foram realizados filtros para quantificar qual o tamanho da base, tamanho das informações que podem ser classificadas como positiva, negativa, etc. Dessa forma, definiu-se para esse filtro que classificações consideradas positivas são equivalentes a 5 e 4 estrelas, neutras 3 estrelas e negativas de 0 a 2 estrelas.  Após isso, temos os seguintes dados:

| Tipos de classificação          | Tamanho dos dados |
| ------------------------------- | ----------------- |
| Todos os tipos de classificação | 99224             |
| Positivas                       | 76470             |
| Neutras                         | 8179              |
| Negativas                       | 14575             |

Entretanto, ao realizar uma avaliação mais detalhada da base de dados, percebe-se que muitas vezes os clientes deixam o número de estrelas equivalente a sua satisfação sobre o produto, mas não deixam um comentário, portanto, encontra-se *reviews* que não possuem comentários, assim, temos os seguintes dados:

| Tipos de classificação | Tamanho dos dados |
| ---------------------- | ----------------- |
| Positivas              | 26530             |
| Neutras                | 3557              |
| Negativas              | 10890             |

Com base nisso, obteve-se uma *wordcloud*, que é uma nuvem com as palavras com maior recorrência em nossa base, desconsiderando qualquer tipo de avaliação sobre o sentimento do comentário, bem como artigos, preposições, etc.

 ![Wordcloud de toda a base utilizada](https://github.com/Caroles12/PI3/blob/main/imagens/todasasclassifica%C3%A7oes.png)

A nuvem de palavras acima é de bastante relevância, pois nos indica um desafio em nosso trabalho: A maior parte dos dados refere-se a entrega do produto e não sobre uma característica do produto, isso possui um impacto relevante nesse trabalho, pois a quantidade de dados que será utilizada para treinamento e resultado final é reduzida, o que nos leva a crer que será preciso adicionar mais linhas que se refiram ao produto, afim de obter um resultado final mais satisfatório.
