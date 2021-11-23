# PI3

# Sobre o projeto

# O que é análise de sentimentos? 
Análise de sentimentos ou mineração de opiniões refere-se ao uso de NLP (processamento de linguagem natural) cujo objetivo é identificar, extrair e quantificar a polaridade expressada nos dados.

# Qual a dificuldade em realizar esse trabalho?
Para o aprendizado da máquina, é difícil trabalhar com metáforas, ironizas, brincadeiras. Além disso, é complexo também se trabalhar com muitos sentimentos em uma sentença, por exemplo:
          "Esse telefone é muito bonito, mas a bateria deixa a desejar".
Nessa sentença, é dificil para a máquina compreender se o objetivo desse usuário foi expressar uma sentença positiva ou negativa. Para esse trabalho, essa é uma sentença relevante, portanto, é um desafio compreender como agregar isso.

# Níveis na análise de sentimento
Existem 3 níveis de análise de sentimento: nível de documento completo, de sentença ou de aspecto. No nível de documento, todo o texto pode ser classificado como positivo, neutro ou negativo. No nível de sentença, o texto é dividido em sentenças, que têm suas polaridades calculadas individualmente. Já no nível de aspecto, são extraídos dos textos
várias entidades e aspectos, e depois é calculada a polaridade para cada um deles.
Nesse projeto **AINDA NÃO ESTÁ DEFINIDO QUAL NÍVEL SERÁ TRABALHADO**.

# Fluxo de dados.
Primeiramente, é preciso realizar uma filtragem dos dados, pois podem ocorrer a existência de caracteres especiais ou emojis, que não podem ser considerados em nossa análise. Após isso, é necessário realizar a mineração desses dados, em que iremos buscar padrões e regras, afim de obter quais são os registros negativos e por fim, o pós processamento do dado, objetivando obter quais foram as palavras negativas mais utilizadas sobre o produto.

![image](https://user-images.githubusercontent.com/40871824/142950430-3d68db30-165e-4793-988c-db8e939b5661.png)
