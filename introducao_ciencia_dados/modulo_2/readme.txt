# Módulo 2 para Introdução a Ciência de Dados

# TL;DR: saber como escolher um modelo e seus hiperparâmetros, o que é um Overfitting e como identificá-lo, os tipos de modelos preditivos e saber
o que é o bias-variance tradeoff. saber o que é um modelo supervisonado, saber criar um laço for para criação de vários plot variando grau de intensidade
do modelo e cálculo erro de teste e treino.

# Conteúdo: 
1. Modelos preditivos
    1.1 Classificação vs regressão
    1.2 Método hold-out
    1.3 Erro do modelo (ex.: rmse)
2. Overfitting
    2.1 Balanço entre N dados e M complexidade do modelo
3. Bias-variance tradeoff
4. Escolhendo modelos
    4.1 Validação Cruzada
    4.2. Casos estratificados

# Bibliotecas utilizadas:
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression --> para importação do modelo linear
from sklearn.preprocessing import PolynomialFeatures --> transforma os dados em uma matriz N por t, onde N é o número de observações e 
                                                         t número de hiperparâmetros
from sklearn.model_selection import train_test_split, cross_validate --> importação da validação Cruzada
from sklearn.neighbors import KNeighborsClassifier --> importação do modelo de K vizinhos, KMN
from sklearn.metrics import accuracy_score --> importação de métricas para mensurar acuracidade do modelo treinado frente ao y_teste

# Aprofundando:

1. Modelo supervisionado, como o nome diz, é um modelo onde damos para a máquina os dados de treino, teste e o output para treiná-lo. O modelo não 
supervisionado, ao contrário, faz com que o modelo aprenda sem ter o output para ensinar.
    1.1 Modelo supervisionado = criança, vc mostra fotos de cachorro, diz que é cachorro, mostra foto de não cachorros e diz que não são cachorros,
    repete até ela aprender. Depois faz um teste, onde mostra uma foto e a criança precisa falar se é ou não cachorro. No caso a criança  = modelo superv.

2. Uma observação empírica é que geralmente = M < N/3 onde M é a complexidade do modelo e N base de dados de treino

3. Validação Cruzada é pegar a base de treino e dividir em partes (chamado de folds) onde 1 fold será para teste e os outros N-1 folds serão para teste.
Roda essa análise trocando que é o fold de teste e para cada iteração ter uma acurácia. A acurácia média das iterações forma a acurácia do modelo para 
aquele hiperparâmetro. Ao mudar o hiperparâmetro, repete o processo. O que tiver maior acurácia média será o melhor hiperparâmetro.

4. Saber como criar ou dividir uma base de dados em dados de treino e dados de teste. Com isso em mente vamos escolher um modelo e averiguar dentro 
dele quais os melhores hiperparâmetros para escolher. 
    4.1 A escolha do hiperparâmetro é feito com ajuda da validação Cruzada
    4.2 Após a definição do hiperparâmetro, treinar o modelo para toda a base de treino (sem a divisão de folds).
    4.3 Após isso, aplicar o modelo na base de testes e medir seu Erro
    4.4 Lembrando que o erro sempre será Y_pred em relação ao y_teste. A função de erro será escolhida por vc. Um exemplo é o 
    RMSE (root mean square deviation).

5. identificação do overfitting, é através de um plot onde para cada grau de complexidade no modelo mede-se o erro com dados de treino e de teste. 
Quando o erro de treino cai, mas o erro de teste sobe, indica que para aquele grau de complexidade o modelo tá sofrento overfitting.

6. Lembre-se que um grau que tenha overfitting pode passar a ser um bom grau de complexidade quando N aumenta. É aqui que se conecta com a regra do M < N/3
se aumento o N eu posso aumentar o M.

7. O modelo linear_model.LinearRegression mostra a relação linear da variável com o hiperparâmetro do modelo, portanto pode ser utilizado para um 
polinômia de grau N**2 ou maior, pois cada termo tem uma relação linear com seu hiperparâmetro. 
Ex.: Y(x) = Teta1 + teta2*x + teta3 * x**2 + teta4 * x**5 + tetan * x**n

8. Storytelling 
    8.1 seleciona base de dados de teste e treino
    8.2. escolha um modelo (LinearRegression, KMN, outros)
    8.3 faça o método de validação Cruzada
    8.4 escolha o melhor modelo com melhor hiperparâmetro através da maior acuracidade dentre o teste de validação Cruzada
    8.5 treine o modelo para toda base de treino
    8.6 aplique o modelo na base de teste
    8.7 defina a forma de mensuração do erro (ex.: RMSE)
    8.8 mensure o erro entre Y_pred e y_test para saber se o modelo escolhido é adequado. Quanto menor o erro, melhor.
    
9. Validação Cruzada é importante para evitar de termos separação de eventos fáceis de predizer para treinar nosso modelo. COm o método vamos ter uma estimativa 
melhor que reduz a variância do modelo.

10. Diferença entre Parâmetro e hiperparâmetro = parâmetro é ajustado pelo algoritmo no modelo a partir dos dados. Hiperparâmetro é setado pelo
humano

11. É comum no mercado usar o ten-fold cross validation (K=10)

12. Acurácia do ten-fold pode ser entendida quantos % dos dados foi acertado.

13. Lembrar de usar np.random.seed(42) para garantir reprodutividade do experimento no computador de outras pessoas e até mesmo no mesmo precisa
em outro momento. Lembrando que todas bibliotecas tem um random seed e o dito anterior é para o np. Portante se estamos usando diversas bibliotecas,
temos que setar diversas seeds. O numero entre () pode ser qqr um, mas a comunidade de python usa o 42 em homenagem geek a um filme kkk.

14. Importante usar shuffle=True no train_test_split para que a base de dados seja misturada antes de criar a separação. O importante,
pois base de dados podem ser construídas seguindo uma ordem que atrapalha uma análise não enviesada. A exceção é timeseries que tem uma ordem
realmente bem definida (no caso a data). 
