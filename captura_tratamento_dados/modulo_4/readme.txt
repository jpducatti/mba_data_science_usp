## ANALISE DE COMPONENTES PRINCIPAIS - PRINCIPAIS

 - Uso: 
 reducao de dimensionalidade, eliminação de ruído, compressão de informação

 - Como funciona:
 conceito: matriz de covariância, mudança de base,  teorema espectral; 
 quociente de Rayleigh

    - Variância de uma coordenada = espalhamento dos dados com relação a coordenada (x ou y)
    que se está olhando. Variância menor =  dados mais concentrados

    - Covariância significa = para valores altos, indica que quando um valor de um sequência
    cresce, a outra sequência também cresce. Exemplo: quando valores de X aumenta, Y tb 
    aumenta. Logo, nesse caso, X e Y covariam de forma similar.
        - É uma medida de grau de interdependência numérica entre duas variáveis aleatórias
        - Logo, variáveis independentes apresentam COVARIÂNCIA = 0.
        - As vezes chamada de medida de dependência linear
        - Lembrando: Variavel aleatória é uma variável q tem os possíveis resultados conhecidos,
            contudo impossíveis de saber antes de acontecer (ou seja depende da sorte)

- ANALÍSE DE COMPONENTES PRINCIPAIS:
    - Objetivo = encontrar uma NOVA BASE para representar os dados de modo que a COVARIÂNCIA
        entre coordenadas distintas nesta nova base seja 0, ou seja, os dados etejam
        descorrelacionados.
            - É pegar variáveis correlacionadas em um conjunto de variáveis 
            lineares não correlacionadas
    - Usos: 
        - Reduzir dimensionalidade ou seja numeros de variaveis dos dados
        - Investigar estruturas multivariadas: dependência / correlação
        - Identificar relações de causalidade e / ou associação              
    - Cuidados:
        - sensível a outliers