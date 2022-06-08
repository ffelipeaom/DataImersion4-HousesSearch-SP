# Projeto de pesquisa e predição de imóveis na cidade de São Paulo
Project for Alura Data Immersion 4, May 2022

[Link para o Collab](https://colab.research.google.com/drive/1tyubfCSsURKhDbF8UrA5WB0Q8j0WhEVR#scrollTo=vH6m6Ch0F4mL)

## Explorando e preparando os data frames
De início, temos três bases de dados para trabalhar, mais uma quarta para georreferenciamento.
1. ***Dados de imóveis.*** Inclui endereço, bairro, metragem, valor em reais, número de quartos, banheiros e vagas.
2. ***Dados do IBGE.*** Inclui variáveis de renda, variância de renda, número de habitantes em domicílio, entre outras variáveis de significância para predição.
3. ***"Endereço".*** Possui também endereços, bairros dos municípios do estado de São Paulo, CEP e suas latitudes e longitudes. 
4. ***Geopackage.*** Convertido do shapefile do IBGE por ser relativamente mais leve e rápido de trabalhar.

### O que foi feito
- ***Dados de imóveis.***
  - Foram tratados os valores da coluna com os valores em reais dos imóveis que estavam em aluguel por dia/mês/ano. 
  - Os valores dessa mesma coluna foram convertidos para tipo numérico, e removido elementos não-numéricos.
  - Foi calculado e adicionado ao data frame, o valor do metro quadrado de cada entrada.
  - Foi criado uma escala em milhões de reais para os valores dos imóveis, que também facilitaria legibilidade em análises e plotagem.
- ***"Endereço"*** foi tratada para ser juntada à base de dados dos imóveis, adicionando variáveis de localidade para cada entrada.
- ***Dados do IBGE*** teve a codificação tratada e então juntada à base de dados dos imóveis, mantendo-se as variáveis de interesse.
- ***Geopackage*** foi utilizado para georreferenciamento.

## Visualizações e análises
Com um data frame mais completo, fez-se algumas visualizações para achar relações entra as variáveis, outliers e outras observações.
Neste histograma, observamos a frequência da quantidade de imóveis por faixas de valores, na escala de milhões. É possível observar que parte significante dessa quantidade se encaixa até aproximadade 2 milhões de reais. É verificável uma correlação da quantidade de imóveis e seu valor: quanto mais imóveis numa determinada faixa de valor, menor seu valor.

![hist_sp](https://user-images.githubusercontent.com/95704769/172647447-89e7b9c5-699a-4c63-8629-e2eb2c4743e3.png)


Nos boxplots abaixo, é observado a variação de dados de metragem, número de quartos, banheiros e vagas, e o valor em reais. É notável o tanto que outliers definem  dessas plotagens; e possivelmente esse aspecto não é apenas visual. Alguns desses outliers podem estar atrapalhando um melhor entendimento dos dados e, consequentemente, uma melhor tomada de decisão.

![boxplot_before](https://user-images.githubusercontent.com/95704769/172651012-adc833ea-96bf-4c91-a3f4-2063334f68fc.png)


## Tratando outliers
Utilizei o método Intervalo Interquartil (Interquartile Range, IQR) para tratar outliers. Este método mede dispersão estatística pela diferença entre o quartil superior e o quartil inferior, realçando a precisão dos dados ao remover pontos periféricos que contribuem pouco para os dados como um todo.
Abaixo, os mesmos boxplots, antes e depois de aplicado o método. Observado-se uma consistência maior nos dados, além da leitura e visualização facilitada, mesmo com a presença de alguns pontos periféricos.

![boxplot_beforeafter](https://user-images.githubusercontent.com/95704769/172656222-d6ed3f7a-f5a9-45d1-82db-f3b65fb883d7.png)



