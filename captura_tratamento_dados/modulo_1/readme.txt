## Captura Tratamento de Dados

1 - tipos de dados: estruturados (os que conhecemos, tabulares) 
e os não estruturados (imagens, textos, som, etc...). O desafio é estruturar os dados
não-estruturados para a sua função


2 - PROBLEMAS DE DADOS:

2.1 - DADOS FALTANTES - importante entender a causa dos dados faltantes com ajuda de 
especialistas de negocio para escolher a melhor técnica para trabalhar
MCAR -  missing completely at random - 
        totalmente aleatório a lá cara ou coroa
MAR  -   missing at random - 
        probabilidade de faltante é independente do conjunto Vm,
        mas apresentam uma relação com outras variáveis do conjunto Vc
MNAR - missing not at random
        É quando o atributo é faltante devido a relação com o próprio atributo.

2.2 - 
OUTLIERS = dado que recai fora da distribuição principal dos dados. Não é um erro
INCORRETO = dado não faltante que não apresenta relação lógica com o que mensura, eg homem
grávido
RUÍDO = dado que atrapalha análise de dados, dificultando encontrar padrões. Pode ser um dado
incorreto ou outlier.

2.2.1 - Forma de encontrar erro: procurar por dados únicos em variáveis quanti discretas
e qualitativas. Se for um dado que não sabemos como corrigir => remover; Se conseguir corrigir
devido alguma pista => corrigir

2.2.2 - OUTLIER - pode ser  dos tipos: 
    1 - ANOMALIAS PONTUAIS OU OUTLIERS GLOBAIS - são ocorrências individuais fora da distribuição principal.
    Usa-se boxplot para encontrá-los e é necessário uma análise de todos outliers globais para
    entender se: 1- Dados factível e inputado corretamente = não fazer nada; 2-) Dados incorretos = remover
    2 -  OUTLIERS CONTEXTUAIS - dados que isolados não são aberrantes, mas com o contexto se tornam um.
    Exemplo: o dado outlier acontece devido a relação com outra variável. O peso de um bebê outlier pode ser
    devido a relação com o atributo Nr de Semanas de Gestação.
    Usa-se boxplots com fatiamento de dados para identificá-los. Se for incongruente => remover
    3 - OUTLIERS COLETIVOS - conjunto de observações cujos valores, quando analisados em grupo,  indicam evento
    não usual. Eg: nascer só bebês do sexo M em um único mês

2.3 - 
DESBALANCEAMENTO - quantidade maior de dados representando certos eventos e menos de outros. Em regressão,
mais dados em um intervalor; em problemas de classificação = uma var categórica tem uma freq maior de valores.
Poder ser causado por: 1) problema de amostragem; 2) problema a priori do dado (é a freq real dos dados)
O tratamento depende do quão desbalanceado está. No caso 1 : 2 a 1 : 3 não representam um grande problema

REDUNDÂNCIA - linhas duplicadas ou atributos constantes e geralmente ambos podem ser removidos (não é uma regra
geral). No caso de atributos é a remoção do atributo (coluna)

3 - PIPELINE GERAL DE COLETA E TRATAMENTO DE DADOS
1 - coleta
2 - pré-processamento (também chamado de ETL)
3 - modelagem
OBS: se os dados são não estruturados, existe um passo 0 que é a ESTRUTURAÇÃO

3.1 - ABRINDO O PRÉ-PROCESSAMENTO
1 - Extrair os dados raw de um datawarehouse / banco de dados com SQL e Spark
2 - Análise do tipo e valores dos atributos -> análise da distribuição dos dados observados. Vou modelar numéricos,
eles são numéricos? os valores estão corretos?
3 - Análise de redundância (linhas duplicadas ou atibutos constantes)
4 - Análise de dados faltantes e outliers -> verificar em quais atributos acontecem, se há uma correlação dos dados
faltantes com outras variáveis. Ao preencher dados, retornar no ponto 3 ( se gerou redundância)
Em outliers, entender as ocorrências de outliers listando as ocorrências. Após tratar os outliers, deve-se
retornar ao passo 2

Geralmente dois ciclos são suficientes para finalizar a etapa de pré-processamento de dados

CUIDADO:
1 - deve-se evitar preencher dados sensíveis (precisa do conhecimento de um especialista para identificar o 
que são dados sensíveis)






