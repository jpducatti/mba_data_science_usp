Conteúdos Abordados:
    1.  K-vizinhos mais próximos.
    2. Regressão Logística.
    3. Naive Bayes

1. K-vizinhos + próximos é um modelo supervisionado usado para classificação baseado na menor distância dos 
atributos a uma classe. Identifica os k-vizinhos mais próximos através da distância, 
ver a classe deles e classificar conforme a classe mais frequente entre os k-vizinhos.
    1. Medida de similaridade (métrica de distância): euclidiana, minkowski
    2. Medida de dissimilaridade: cosseno, pearson
    3. K muito baixo fica overfitting e K muito alto gera underfitting
    4. Para encontrar o melhor K, utilizar a validação cruzada para encontrar o melhor K
    5. Modelo não paramétrica porque não apresenta nenhum parâmetro para ajustar (o K é um hiperparâmetro)
    6. É um classificador não-linear
    7. Por utilizar distância nos cálculos, precisa normalizar ou padronizar os dados

2. Regressão Logística: usa a função logística como modelo para predição. Procura-se estimar o Beta por máxima
verossimilhança. Para uso de 3+ classes, usa-se o one-hot encoding para classificação.


3. Naive Bayes: classifica conforme a maior probabilidade de pertencer a uma classe. Usa o teorema de bayes, 
multiplicando a probabilidade de cada atributo. Se os aributos forem contínuos, considera que tem distribuição
normal, calcula a média e variância e assim calcula a probabilidade de x ser de determinada classe.
Robusto a ruídos e atributos não relevantes.



