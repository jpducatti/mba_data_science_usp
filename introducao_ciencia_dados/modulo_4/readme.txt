# Módulo 2 para Introdução a Ciência de Dados

# TL;DR: definir o agrupamento utilizado, definir similariedade entre os objetos, definir medida de proximidade,
definir se utiliza medida de similariedade ou dissimilariedade, saber avaliar o agrupamento, 
saber como descobrir número de clusters no K-means

# Conteúdo: 
1. K-means
2. Agrupamento Hierárquico

# Aprofundando:
1. Classificação = Classificação supervisionado, tem conjunto de exemplos

2. Agrupamento = Classificação não-supervisionado

3. Problemas encontrados: definir medida de proximidade ou não-proximidade (medida de distância) entre os
objetos, definição do que é uma similariedade.
    3.1 Métrica de dissimilariedade: distância euclidiana, distância de minkowski
    3.2 Métrica de similariedade: distância cosseno, distância de pearson

4.  Estágios:
    1. Definir medida de proximidade
    2. Definir crtiério de clusterização
    3. Definir algoritmo de clusterização
    4. Validação dos resultados

5. k-means
    5.1 Sensível a posição inicial da semente
    5.2 precisa definir o número de clusters (pode-se usar o método do cotovelo)
    5.3 Sensível a cluster com densidade de objetos diferentes
    5.4 sensível a cluster com volumes de dados diferentes
    5.5 Não funciona para clusters lobulares

6. Agrupamento Hierárquico
    6.1 Método funciona definindo a matriz de proximidade entre os dados
    A união dos clusters no dendograma é feito por 4 métodos:
        6.1.1 Single linkage = pega a menor distância entre os objetos dos dois clusters para uní-los
        6.1.2.Complete linkage = pega a máxima distância entre todos os objetos para unir os clusters
        6.1.3 Average Linkage = pega a distância média entre os objetos para unir os clusters
        6.1.4 Ward linkage = utiliza distância aos centroides para agrupamento dos cluster 
    6.2 Pontos (-) do agrupamento hierárquico
        6.2.1 Nem sempre fornece a melhor slução
        6.2.3 Sensível a outliers
        6.2.4 Melhor utilizado para dados numéricos pois usa distância

7. Analisando Agrupamentos para 1) evitar encontrar padrões em ruídos,
para comparar diferentes métodos de agrupamentos (k-means vs agrupamento hierárquico) 
e para comparar clusters (single vs complete vs ward vs average linkage).
    7.1 Pode avaliar por um índice externo (eg medida de entropia) ou indice interno (medida de erro)
    7.2 Indice externo precisa ter a classificação conhecida para comparar 
        Adjusted Rand Score (uma medida de erro)
        Normalized Mutual Info Score (baseado na entropia de shannon)
    7.3 Indice interno, não precisa da classificação conhecida
        Silhouette Score (medida de pureza)
