## MODULO 3
## DISCRETIZACAO, NORMALIZACAO, TRANSFORMACAO, CODIFICACAO E ONE-HOT ENCODIGN

1. DISCRETIZACAO --> utilizado para transformar variáveis continuas com infinitos valores em variáveis 
categóricas (discretas). Agrupamento é uma discretização que leva em consideração duas variáveis ao mesmo
tempo para realizar o agrupamento.
Exemplo: algoritmo nao-supervisionado cria clusters para agrupar os valores. Precisa conhecer o método
de agrupamento e a distância utilizada no agrupamento
Pode agrupar com intervalos uniformes, com distribuicao uniforme (quartil) ou utilizando agrupamento com modelo

2 - NORMALIZACAO e PADRONIZAÇÃO - a depender do modelo, precisamos padronizar os dados para evitar que um modelo
dê peso diferente para cada variável / coluna. Muito utilizado em modelos que usa distância na classificação
Tipos: min-max ; pela média; robusta por quantis; z-score (whitening or standard scaler); normas (L1, L2 ou pelo maximo)

Geralmente as normas são utilizadas para normalizar valores dentro de uma linha, enquanto as outras é para normalizar
uma coluna inteira

**Algoritmos que comumente esperam dados normalizados/padronizados** (lista não exaustiva)

* LinearRegression
* KNeighborsRegressor
* PCA
* LinearDiscriminantAnalysis
* MLPRegressor
* SVC


3 - TRANSFORMACAO DE ATRIBUTOS
A trasnformação não exclui a limpeza de dados e inclusive pode gerar novos atributos;
Variáveis apresentam distribuição diferentes e senso comum de que seguem distribuicao uniforme ou normal
ou que correlações são lineares são errôneos (o senso comum);
Transformar variáveis ajuda a a analisar os dados. Exemplo, transformar dados exponenciais em lineares
com função logarítmica;
Raiz Quadrada também é utilizada para transformar os dados, no caso dados quadráticos;

4 - ASSIMETRIA OU SKEWNESS
É uma medida de simetria dos dados (ou assimetrica), para observar quão normal os dados são;
Para transformar pode ser utilizado as funções dados pela tabela da aula ou usar o PowerTransformer do
sklearn;

5 - CODIFICAO VARIAVEIS CATEGORICAS
Variáveis categóricas, geralmente expressas por meio de texto, não são utilizáveis diretamente 
por parte dos modelos estatísticos e computacionais;
Obter codificações numéricas dessas variáveis se torna importante para permitir análise por um 
número mais amplo de ferramentas;

6 - CODIFICACAO ONE-HOT CODE OR DUMMY VALUES
A + adequado para aprendizagem de máquina, transforma categorica em numericas em valores binarios 
para indicar presença (valor 1) ou ausência (valor 0)












