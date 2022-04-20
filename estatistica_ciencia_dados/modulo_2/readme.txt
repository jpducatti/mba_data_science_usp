## PROBABILIDADES

1. experimento aleatorio = experimento que pode ser executado infinitas vezes sem alterar as condições dos experimento
eg.: jogar dado, lancar moeda, fabricar uma peca e encontrar peca defeituosa ou normal

2. espaco amostral  = conjunto de todas as saidas do experimento. 
Evento é um subconjunto do espaco amostral, ou seja, a selecao de um ou mais possiveis outputs
eg: dado = {1,2,3,4,5,6}. evento A = {numeros pares}

3. evento mutuamento exclusivo = quando a interseccao de dois eventos é impossível
eg.: a = numero par; B = numero impar --> ambos sao eventos mutuamente exclusivos

4. Definicao KOLMOGOROV = probabilidade é é a soma de definicao de probabilidade de eventos mutuamente exclusivos, variando de 0 a 1
Definicao frequentista = a probabilidade de um evento é igual a sua frequencia de ocorrencia em muitos experimento. 

5. Probabilidade uniao A e B = p(A) + p(B) - p(A uniao B) --> pq remete a regiao do meio 2x e por isso retira 1

6. Probabilidade condicional --> chance de ocorrer A ocorrer dado B OCORREU. Essa probabilidade altera o tamanho amostral, pois o evento B já occoreu.
Pensando no Diagrama de Veins, se B ocorre o espaço amostral passou da união de A e B para região de B. A unica parcela de A possivel nesse novo
espaço amostral é a região de A dentro de B, ou, P(A interseccao B), dentro do novo espaco amostral que é P(B)
P(A|B) = P (A interseccao B) / P (B), sendo P(B) > 0


7. Eventos independentes = A e B serão independentes se e, somente se, P (A interseccao B) = P(A)*P(B)
Se são independentes, a probabilidade condicional de P(A) não vai ser impactada pelo P(B), ou seja, o espaço amostral de A não será alterado dado que B occoreu.
Assim, P(A|B) = P(A interseccao B) / P(B) = P(A) --> logo P (A interseccao B) = P(A)*P(B)
Exemplo pratico: dado que dado saiu par, qual a probabilidade de uma moeda ser par? São eventos independentes pq o evento inicial do dadi dado não impacta o 
espaço amostral da moeda.

8. Teorema de Bayes - MT IMPORTANTE
Particao do espaco amostral, presente no teorema --> pense em um quebra cabeca onde cada peça é uma particao.
As peças nao se sobrepoe, logo Bi interseccao Bi+1 = vazio (Bi é a particao) e a uniao de todas particoes é equivalente ao espaco amostral
O evento A seria um desenho no quebra cabeca formado e orestante é o plano de fundo.

9. Variavel aleatoria - é uma função que associa um valor real a cada elemento do espaço amostral.
0 <= P (X = x) <= 1
P (X = x) >=0
P(a <= X <= B) = somatoria de x=a até x=b (P (X=x))
Podemos ter uma variável aleatória discreta ou contínua.
No caso de contínua, a variável aleatória tem uma função chamada de densidade de probabilidade

