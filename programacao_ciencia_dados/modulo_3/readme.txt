# Documento Read-me comentando os ensinamentos do módulo

Aula 3 do Curso de Programação para Ciência de Dados

TL;DR - entender como importar módulos e pacotes e suas diferenças; ler, escrever e modificar arquivos através da programaçõ python; funções 
do pyhton e sua utlização; noção básica de classes e objetos

# Conteúdo:
- Módulos e pacotes
- Programação Funcional
- I/O em python
- Noções básicas de classes e objetos

__Referências:__
- Mark Lutz, Learning Python, O'Reilly, 2013
- Eric Matthes, Python Crash Course: A Hands-On, Project-Based Introduction to Programming, No Starch Press, 2015 

-------------------------------------------

1. MÓDULOS são arquivos que podem ser importados no python e PACOTES são módulos que contém vários
módulos, podendo incluir subpactoes. Ex de pacote = Numpy onde dentro tem vários módulos que
importamos. Dentro de cada módulo temos ATRIBUTOS E MÉTODOS que usamos para importar especificamente;

2. Podemos importar módulos através do comando IMPORT e do FROM. O IMPORT carrega todo o pacote
enquanto FROM importa elementos específicos de um módulo.
    2.1 Principais pacotes e módulos usados no curso:
        Numpy
        matplotlib
        pandas
        sklearn
        Math
        sys
    2.2 Estrutura:
        from nome_do_modulo import * (importa tudo do modulo)
        import nome_do_modulo
        from nome_do_modulo import nome_do_método (importa um método especifico)
        import nome_do_modulo.nome_do_método

3. Contéudo de um módulo por ser acessado pelo método dir(nome do modulo). eg: dir(sys). Para saber 
onde no disco guarda o módulo, usar print(modulo.path)

4.  PROGRAMAÇÃO FUNCIONAL
    map:    aplica uma função definida anteriormente (ou lambda) em todos elementos de uma sequência
            ou iterador. Output é um objeto. USO = aplicar o x**2 a todos elementos de uma lista.

    filter: aplica uma função definida anteriormente (ou lambda) a elementos de um iterador, retornando
            elementos da sequência que satisfaz a função. A função especificada tem que retornar 
            True ou False. Output do filter = objeto. USO = filtrar elementos de uma lista com base em um
            função.

    reduce: necessita ser importado dom módulo functools. Aplica uma função definida anteriormente
            (ou lambda) acumulativamente a um iterador, da esquerda para a direita, reduzindo a sequência
            em apenas 1 elemento. A função passada TEM QUE TER 2 ARGUMENTOS (um onde será acumulado e
            o outro o valor a ser acumulado). Output de reduce = um elemento (int, float, string).
            USO = realizar operaçãoes de acumulação de elementos de uma lista, tipo x =  x +y
    
    A programação funcional é computacionalmente mais eficiente que laços for. Sempre que possível
    evitar laços for, usando COMPREHENSION ou proramação funcional.

5. Python manipula arquivos ascii e sempre le conteúdo como string. Portanto, números tem que ser
transformados em int e float. 
    5.1 O comando OPEN abre arquivos em diferentes modos. São eles:
        'r' = para read do arquivo
        'w' = para write no arquivo
        'a' = para append no arquivo (acrescentar conteúdo)
        'r+' = para read e write
    5.2 Através do comando %%writefile nome_do_arquivo.txt, podemos criar um arquivo text no python.
        Para ler o seu conteúdo (e não informação sobre o arquivo em si no modo 'r'), podemos utilizar
        
        Read(size)  = lê size em bytes. Se omite syze, le o arquivo inteiro.
        readline()  = lê uma única linha do arquivo
        readlines() = retorna uma lista com todos elementos do arquivo como elemento da lista
        for line in f = lê cada linha do arquivo atribuindo-a a varíavel line
    
    5.3 Exemplo de como ler o conteúdo do arquivo txt criado:
        f = open('data.txt','r')  # abre o aquivo criado com o comando '%%writefile data.txt'
        lines = f.readlines()  # lê todas as linhas do aquivo e armazena na lista 'lines'
        print(lines)

    5.4 Para escrever em arquivos, usa-se:
        write = escreve UMA STRING no arquivo
        wrtielines = escreve UMA LISTA no arquivo

6. PROGRAMAÇÃO ORIENTADA A OBJETOS:
    //difícil resumir, melhor olhar a aula//
    6.1 Classes são capazes de herdar estados e comportamentos de outras classes por HERANÇA. A classes
         herdade é chamada de superclasse ou classe base. A classe que herda chama-se subclasse.

    6.2 Classe é um protótipo para criar um objeto. Quando um objeto é criado de um protótipo, diz-se 
        que ele foi instanciado. Uma classe especifica os atributos e métodos do objeto que pode ser
        instanciado quantas vezes quiser.
    
    6.3 Objeto apresenta ESTADO e COMPORTAMENTO. Estado = informaçãoes salvas nos atributos do objeto
    COMPORTAMENTO = manifestado através de métodos associadas ao objeto.

