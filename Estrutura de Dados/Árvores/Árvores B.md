---
aliases:
  - b_tree
tags:
  - ED/Árvores
date: 2023-10-10
time: 15:11
complete:
---
# Árvores B

> $\textit{Definição.}$ Estrutura de dados de árvore binária de busca que possui capacidade de armazenar múltiplas chaves em um mesmo nó, aumentando a eficiência de operações para acessar o disco.

Por definição, as árvores B são regidas pelos seguintes princípios:

1. Se um nó possui $k$ chaves e não é uma folha, então ele possui $k+1$ filhos.
2. Em uma árvore B de ordem $d$, todo nó **exceto a raiz** possui entre $d$ e $2d$ chaves de modo que a raiz possui entre 1 e $2d$ chaves.
3. Os filhos só podem ser nulos nas folhas.
4. As chaves de cada nó são ordenadas semelhante a uma [[Estrutura de Dados/Árvores/Árvore 2-3-4|árvore 2-3-4]].

- [i] Podemos definir a árvore 2-3-4 como uma árvore B de ordem 3 em que cada nó pode ter entre $\lfloor \frac{d}{2} \rfloor$ e $d$ chaves **(definição alternativa)**.

## $\texttt{Busca.}$

A busca em uma árvore B possui complexidade $h\log d$ de modo que $d$ é a ordem da árvore (número mínimo de chaves em um nó).

## $\texttt{Inserção.}$

- [i] Toda inserção em uma árvore B ocorre nas folha.

Para inserir um elemento em uma árvore B, primeiro usamos o algoritmo de busca para localizar a posição onde o novo elemento deveria ser inserido. Uma vez identificada essa posição, reservamos espaço no bloco sequencial correspondente ao nó e adicionamos a chave desejada. Em seguida, verificamos se a quantidade de chaves no nó excede o limite permitido, desencadeando o processo de **cisão** ou divisão do nó.

Considere preenchemos o nó inicial com o número máximo de chaves permitidas (geralmente $2d$). No entanto, quando ultrapassamos esse limite, executamos o processo de **cisão**, o qual consiste em dividir o nó em dois, movendo a chave do meio para um nível superior na árvore, se necessário.
![[Inserção Árvore B.svg]]

Eventualmente, a raiz também sofrerá uma cisão, fazendo com que a mesma se divida em três nós de modo que o fator intermediário se torne a nova raiz.

- [i] A complexidade do algoritmo de inserção corresponde a $\mathcal{O}(h\log d+dh)$, uma vez que apenas pegamos a complexidade da busca e somamos à complexidade da alocação inicial necessária para inserir a chave. Como essa última complexidade pode ser propagada, apenas multiplicamos por $h$, resultando em $dh$.

### <span style="color:#ff0000">Tem mais coisa em Remoção.</span>

## $\texttt{Remoção.}$

- [i] A remoção em árvores B **ocorre apenas nas folhas**. Posto isso, devemos substituir as chaves do nó pai com as das folhas para que a remoção seja feita.

O processo de remoção em uma árvore B envolve a análise de alguns casos. De um modo geral, identificamos dois casos principais:

1. **Concatenação**: Quando tivermos um nó com $d$ chaves e outro com $d-1$ chaves, poderemos aplicar o método da **concatenação**, isto é, realizamos o processo oposto da cisão e "abaixamos" uma chave do nó pai de modo que os dois filhos restantes sejam juntados. 

Suponha o seguinte exemplo no qual desejamos remover a **chave 44**.

![[Concatenação Árvore B.svg|750]]
Vale notar que a concatenação pode se propagar na árvore caso o nó pai conter d-1 chaves e por aí em diante.

![[Árvores B e Heap Binária.mp4]]

2. **Redistribuição**: Quando tivermos um nó com $d+k$ chaves e outro com $d-1$ chaves ao lado, podemos empregar o método da **redistribuição**, isto é, substituímos uma chave do nó pai por uma do filho esquerdo (com $d+k$ chaves) e passamos esse chave de cima para o nó à direita.

Novamente, aqui vai uma ilustração.

![[Redistribuição em Árvore B.svg]]

Por fim, você terá um nó à esquerda com $d+\lfloor \dfrac{k}{2} \rfloor$ chaves e o outro à direita com $d+\lfloor \dfrac{k}{2} \rfloor -1$ chaves.

- [i] A complexidade do algoritmo de remoção é o mesmo que em inserção, ou seja, $\mathcal{O}(h\log d+dh)$, tendo em vista que a remoção pode se propagar para os nós acima.

### <span style="color:#ff0000">Preciso refazer essa seção daqui.</span>

## $\texttt{Altura.}$

Podemos tentar criar uma árvore com o número mínimo de chaves e analisar a evolução da quantidade de nós e de chaves conforme descemos nos níveis da árvore. Posto isso, se considerarmos uma árvore em que todo nó contém $d$ chaves teremos a seguinte tabela.

| nível |   # de nós   |     # de chaves     |
| ----- |:------------:|:-------------------:|
| 1     |      1       |          1          |
| 2     |      2       |        2$d$         |
| 3     |   2$(d+1)$   |   2$(d+1)\cdot d$   |
| 4     | 2$(d+1)^{2}$ | 2$(d+1)^{2}\cdot d$ |
| 5     | 2$(d+1)^{3}$ | 2$(d+1)^{3}\cdot d$ |

Portanto, em um nível $h$ teremos:

1. $\#$ total de nós: $2(d+1)^{h-2}$.
2. $\#$ total de chaves: $2(d+1)^{h-2}\cdot d$.


