## Modelos de Regressão

## Passo-a-Passo

1 - limpeza dos dados
2 - modelagem linear ou simples, elencando as premissas usadas (normalização do erro, variáveis independentes)
3 - análise de diagnóstico do modelo
4 - avaliação do modelo

--------------------

1 - predizer variáveis resposta através de variáveis preditoras, utilizando modelos lineares (simples e múltipla)

2 - Y = variável aleatória observáveis (resposta); X = variável preditora conhecida, ou seja, não-aleatória; 
beta = parâmetro a se estimar; sigma = erro aleatório

3 - Assumimos:
    3.1 -  normalidade dos erros, com média = 0 e dsv.padrão = (sigmaˆ2)
    3.2 - beta = fixo, não apresenta distribuição de probabilidade (poderia se considerado contexto bayesiano)
    3.3 - X = variáveis independentes

4 - ESTIMAÇÃO DOS PARÂMETROS, beta
    4.1 - método dos mínimos quadrado (EMQ ou MQO)
    4.2 - método da máxima verossimilhança (EMV)
        4.2.1 - considerando a premissa de erro com média 0 e dsv padrão sigmaˆ2, o 4.2 é o mesmo que 4.1

5 - COEFICIENCE DE DETERMINAÇÃO DO MODELO
    5.1 - rˆ2 e rˆ2 ajustado. O segundo leva em consideração a variabilidade do modelo conforme aumenta o número de 
    covariáveis. Em Regressão simples, rˆ2 = rˆ2 ajustado
    5.2 - Em um modelo de Regressão linear simples, o rˆ2 e rˆ2 ajustado é equivalente ao (coeficiente de pearson)ˆ2

6 - ANÁLISE DE DIAGNÓSTICO
    6.1 Resíduo = Y real - Y predito.
    6.2 - Espera-se que o gráfico de resíduo (eixo y) e y predito (eixo x), não apresente nenhum padrão e tenha
    comportamento aleatório
    6.3 Outros resíduos:
        6.3.1 - resíduo studentizado internamento e resíduo studentizado externamente
    6.4 - Identificação de pontos influentes: DFFITS e Distância de Cook
    6.5 - PONTOS DE ALAVANCA: pontos outliers no espaco dos X, mas não necessariamente são pontos influentes
    , ou seja, outliers que influenciam a predição dos parâmetos Beta
    6.6 Testes de hipóteses podem ser aplicados para identificar padrão nos resíduos
    https://docs.ufpr.br/~taconeli/CE07118/Aula5.pdf


7 - SELEÇÃO DE MODELOS
    7.1 - validação com bases de treinamento e teste e validação cruzada (K-fold cross-validation)
    7.2 - Método Lasso 

8 - MÉTRICAS PARA AVALIAR A QUALIDADE DO AJUSTE
    8.1 Erro absoluto média (MAE); Erro Quadrático Médio (MSE); Raiz do Erro Quadrático Médio (RMSE)
    Akaike Information Criterio (AIC)


