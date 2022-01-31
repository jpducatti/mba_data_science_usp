# Primeiro módulo para o curso Introdução à Ciência de Dados

# TL;DR: saber calcular medidas de posição, medidas de dispersão, coeficiente de correlação spearman e pearson e calcular 
entropia de shannon e entropia relativa de KL, saber criar histogramas, saber usar pyplot para plotar gráficos

# Conteúdo
1. Medidas de posição
    1.1 Moda
    1.2 Média
    1.3 Mediana
    1.4 Criar histogramas
2. Medidas de Dispersão
    2.1 IQR
    2.2 Separatrizes: Quartis, Percentis
    2.3 Amplitude Total
3. Correlação
    3.1 Coeficiente de pearson
    3.2 Coeficiente de spearman
4. Medidas de Entropia
    4.1 Entropia de Shannon
    4.2 Entropia relativa (divergência de Kullback-Leibler)

# bibliotecas usadas
from statistics import mode
import numpy as np 
import matplotlib.pyplot as plt #biblioteca gráfica para mostrar os gráficos
from scipy.stats import iqr
from scipy.stats import pearsonr
import pandas as pd # biblioteca pandas
import seaborn as sns
from scipy.stats import pearsonr, spearmanr
from scipy.stats import entropy

#Aprofundando

1. Coeficiente de Pearson é um coeficiente usado para anlisar a relação linear entre as variáveis. Quando há variáveis altamente correlacionadas, 
é adequado remover uma delas para reduzir a redundância dos dados. Varia entre -1 e 1, onde -1 é altamento anti-correlacionado, 1 altamente 
correlacionado e 0 sem correlação. 
    1.1 Medida de correlação não mede se as variáveis são independentes. Para isso, deve-se verificar a probabilidade condicional. Se X é independente
    de Y, então P (X|Y) = P(X) e P (X,Y) = P(X)*P(Y)

2. Correlação de Spearman é similar ao coef de Pearson, contudo analisa a ordem dos dados e avalia a relação monotônica (ou seja relações lineares e não lineares) de duas variáveis contínuas ou ordinais e não é sensível a assimetrias e outliers nos dados.
    2.1 Basicamente, pensa assim: se X sobe e Y sobe, isso garante um alto valor para coef. de spearman, mas não necessariamente para pearson

3. A entropia de shannon é uma maneira de medir a (in)dependência de variáveis. 

4. A divergência de Kullback-Leibler é usado para comparar distribuições e quanto mais próximo de 0, menor é a perda de informação ao usar a distribuição 
X para prever a distribuição Y e mais similares são as distribuições.
    4.1 Dkl (p||q) != Dkl (q||p) e Dkl (p||p) = Dkl (q||q) = 0 (pois indica a mesma distribuição)

