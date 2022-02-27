# Links uteis
https://www.ufrgs.br/reamat/AlgebraLinear/livro/s11-autovalores_autovetores_e_autoespax00e7os_associados.html
https://scikit-learn.org/stable/data_transforms.html

# --- Aula 3 Tratamento e Transformacao de Dados ---

# Conteúdo: 
1. Tratamento de Dados
2. Transformação de Dados
3. Dados desbalanceados
4. Amostragem
5. Outliers
6. PCA

------------------

1. Tratamento de dado:
    1.1 Eliminação manual de atributos irrelevantes para o aprendizado de máquina
    1.2 Remover atributos que apresentam o mesmo valor para cada objeto
    1.3 Remover objetos com valores NaN, ? e outros valores estranhos
    1.4 Remover linhas duplicadas
    1.5 Para objetos com valores ausentes, remover ou adicionar outro valor que pode ser a média
    1.6 Mais sobre como usar o tratamento de dados:
    https://medium.com/@sunils0506/types-of-transformations-in-machine-learning-5e397a6c9ab4
    1.7 Limpeza de dados: procurar por dados incongruentes para remover, ou dados redundantes. E.g: idade < 0

2. Transformação de Dados:
    2.1 Normalização de valores entre [0,1]
    2.2 Padronização para média = 0 e std = 1

3. Conversão de variáveis nominais para inteiros:
    3.1 One-hot encoding: que cria uma coluna para cada objeto atribiuindo valor de 1 e 0

4. Dados desbalanceados:
    4.1 Usar histograma para verificar o desbalanceamento de objetos em cada classe

5. Outliers:
    5.1 Verificar distribuição dos dados. Pode utilizar a biblioteca seaborn para fazer o gráfico
    5.2 Uso da distância interquantil para encontrar outliers de forma simples. Outlier = Q1 - 1.5*IQR
    ou Q3 + 1.5*IQR

6. PCA - Análise dos Componentes Principais
    6.0 É utilizado para seleção de atributos dentre os possíveis
    6.1 O PCA analisa a correlação entre atributos de forma a eliminar um dos para diminuir redundância nos dados
    E.g: salário e nível de escolaridade da pessoa

Código para averiguar o quanto da variância dos dados é explicado pelo número de componentes:
    pca = PCA().fit(X)
    plt.figure(figsize=(8,5))
    ncomp = np.arange(1, np.shape(X)[1]+1)
    
    # mostra a variância acumulada
    plt.plot(ncomp, np.cumsum(pca.explained_variance_ratio_), 'ro-')
    plt.xlabel('number of components', fontsize=20)
    plt.ylabel('cumulative explained variance', fontsize=20);
    plt.xticks(color='k', size=20)
    plt.yticks(color='k', size=20)
    plt.grid(True)
    plt.show(True)







