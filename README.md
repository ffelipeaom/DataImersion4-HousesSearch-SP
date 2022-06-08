# Projeto de pesquisa e predição de imóveis na cidade de São Paulo
Project for Alura Data Immersion 4, May 2022

[Link para o Collab](https://colab.research.google.com/drive/1tyubfCSsURKhDbF8UrA5WB0Q8j0WhEVR#scrollTo=vH6m6Ch0F4mL)

## Explorando e Preparando os data frames
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
- ***"Endereço"*** foi tratada para ser juntada à base de dados dos imóveis, adicionando variáveis de localidade para cada imóvel.
- ***Dados do IBGE*** teve a codificação tratada e então juntada à base de dados dos imóveis, mantendo-se as variáveis de interesse.
- ***Geopackage*** foi utilizado para georreferenciamento.
