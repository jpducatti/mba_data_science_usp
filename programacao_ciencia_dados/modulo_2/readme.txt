# Documento Read-me comentando os ensinamentos do módulo

Aula 2 do Curso de Programação para Ciência de Dados

TL;DR - utilizar estrutura comprehension, aplicar lambda em alguns momentos em vez de def function, nested for ("for dentro de for"), 
saber estruturas de python para manipulação de listas, strings e tuplas 

# Conteúdo:
- Estrutura IN e NOT IN (não dentro do for)
- Operação com sequências
- Estrturas de python para remoção de valores
- Estruturas de inserção de elementos em lista
- comprehension
- Lambda function     

-------------------------------------------

1. Estruturas para medir performance do código:
    id(variavel) = retorna endereço de memória; 
    %%timeit =  retorna tempo médio de execução do bloco
                de código;

2. REFERENCIAMENTO DE VARIÁVEIS E ENDEREÇO DE MEMÓRIA:
    Uma variável y referenciar um x NÃO CRIA UM NOVO ENDEREÇO DE MEMÓRIA. O y acessa o endereço do x e por isso retorna o mesmo valores. Por isso, 
    se y for uma lista e fizer append, o efeito vai ser aplicado indiretamente a x que y referencia, modificando o valor de x;

3. OPERAÇÕES E MUDANÇAS DE MEMÓRIA:
    Variáveis dos tipos Strings, números e tuplas  criam um endereço de memória único e qualquer operação com essas variáveis IRÁ CRIAR OUTRO ENDEREÇO DE MEMÓRIA. Ex.: x = x+1 cria um endereço diferente de x caso onde x inicial = 3;
    Para lista o acima é verdadeira se usar OPERADORES GERAIS (+ e *). Operadores exclusivos não criam nova lista com novo endereço de memória

4. Estrutura IN e NOT IN:
    é muito interessante para pesquisa de elementos em uma string, lista, ou chave de um dicionário. Bom para pesquisar se um Dado está presente na sua sequência;

5. OPERADORES DE ELEMENTOS EM SEQUÊNCIAS (lista, tupla e string) -->  "*" e "+" podem ser utilizados para manipular sequências. Em tuplas, listas e strings, gera-se sequências com novos endereços de memória; Listas e tuplas com os operadores são acrescentadas como elementos dentro da lista, em strings as palavras se juntam.

6. OPERADORES EXCLUSIVOS DE ELEMENTOS DE LISTAS: 
    CONCATENÇÃO:
        append = insere um elemento ao final da lista. Pode ser inserida uma nova lista como elemento dentro da lista atual; 
        insert = insere um elemento, indicando a posição de inserção. Pode ser inserida uma nova lista como elemento dentro da lista atual; 
        extend = insere uma nova lista como elementos separados na lista. OU SEJA, NÃO INSERE A LISTA COMO UM ELEMENTO LISTA;
    GERAL:
        index = retorna a posição na lista da primeira ocorrência do elemento pedido;
        count = conta número de ocorrências de um elemento pedido;
        reverse = reverte a ordem dos elementos de uma lista, modificando a mesma lista. Não altera o endereço de memória;
        sort =  orderna os elementos da lista conforme o input oferencido. Se input = (), ordenda do menor para maior. Se (reverse = True), vai do
                maior para os menor. Não altera o endereço de memória
    REMOÇÃO:
        remove = remove a 1a ocorrência do elemento pedido;
        pop = remove o último elemento da lista
        del = remove o elemento da POSIÇÃO indicada;
    

7. DIFERENÇA ENTRE OPERADOR EXCLUSIVO DE LISTA E DE OPERADORES GERAIS:
    Append, insert e extend MODIFICAM A MESMA LISTA (mesmo endereço memoria). + e * CRIAM NOVA LISTA (novo endereço de memória);

8. OPERADORES NATIVOS DO PYTHON QUE OPERAM SEQUÊNCIA:
    sorted = ordena a sequência, não modificando a original e criando uma nova lista com um novo endereço na memória. Difere de SORT EM LISTAS, pois sort não cria nova lista e modifica a original
        >>> muito útil para transforma uma string em lista, onde cada letra é um elemento
    max = retorna o maior elemento da sequência
    min = retorna o menor elemento da sequência

9. COMPREHENSION:
    Recurso do python que permite realizar estruturas de laço FOR mais eficientemente. Pode-se medir isso com o %%timeit
    Estrutura => l = [i**2 for i in range(-100,100)]
    Aceita-se IF, ELIF e ELSE na estrtura do comprehension:
        Se tiver só IF, a estrutura é assim => l = [x**2 for x in range(-10,10) if x%2 != 0]
        Se tiver ELSE, muda a estrutura => l = [x**2  if x%2 != 0 else 0 for x in range(-10,10)]
    Aceita-se nested for:
        Estrutura => l = [x+y for x in range(-10,10) for y in range(10) if y < x]
    Comprehension pode ser utilizado para construir dicionários:
        estrutura => dicionario = {expressao_chave:expressao_valor for variavel_local in objeto} -> exemplo dt = {x:x**2 for x in range(10)} 

10. FUNÇÃO:
    Pode ser criado com DEF ou LAMBDA;
    DEF precisa ter return para o computador saber o que retornar. Se não tiver return, a função tem output = None
    Em DEF, pode ser informado os inputs padrões da função caso não seja definida no seu invocamento.
        estrutura => def echo(x=10,y=7):
    Pode-se usar uma função como parâmetro de outra função.
        estrutura => def invoca_echo(f,t): onde f é uma função definida anteriormente

11. LAMBDA:
    É uma função que não recebe nome e é usada in line de outros códigos, INCLUSIVE COM COMPREHENSION estrutura
    Estrutura => f1 = lambda x: x**2 que seria o mesmo que def f1(x): return(x**2)
    Estrutura com comprehension => lnumeros = [i for i in range(10) if f3(i) == 'even'], onde estamos criando uma lista e f3 é a função lambda
    