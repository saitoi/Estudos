---
aliases:
  - heap_binomial
tags:
  - ED/Árvores
date: 2023-10-19
time: 14:14
complete:
---
# Heap Binomial

> $\textit{Definição.}$ Estrutura de dados que consiste em uma coleção de árvores binomiais de ordens distintas de modo que cada árvore binomial segue uma propriedade específica de heap (no caso de heap mínimo que estamos trabalhando).

- [i] Definimos a **ordem** de uma árvore binomial como o número total de filhos da raiz ligados à raiz.

De antemão, precisamos definir o conceito de <ins>árvore binomial</ins>, isto é, uma estrutura de árvore recursiva de modo que os nós são conectados hierarquicamente e, ademais, possuem um limite de nós máximos com base na **ordem** da árvore.

Aqui estão a configuração padrão das árvores binomiais $B_{i}$ iniciais.

![[Árvores Binomiais|600]]

A construção de uma árvore binomial qualquer $B_{i}$ envolve o processo conhecido por **subordinação** que pode ser feito de forma recursiva dada a estrutura desse tipo de árvore. 

Suponha que desejamos criar a árvore $B_{3}$ e, para que isso ocorra, deveremos *subordinar* o $B_{2}$ em função de outro $B_{2}$. Aqui vai uma ilustração gráfica do processo.

![[Subordinação Binomial.svg]]

Esse processo de subordinação pode ser aplicado para a criação de quaisquer árvores $B_{i}$, basta termos duas $B_{i-1}$. 

O **número máximo de nós** em uma árvore binomial $B_{i}$ corresponde a $\lvert B_{i} \rvert=2^{i}$.

Desse modo, para a criação de uma **heap binomial**, basta termos uma **coleção dessas árvores binomiais**. Portanto, o seguinte conjunto de árvores binomiais é suficiente para termos uma heap binomial.

![[Exemplo de Heap Binomial.svg|center|500]]

## $\texttt{Inserção.}$

O processo de inserção em uma heap binomial é relativamente simples. Basta inserirmos um novo nó que será correspondente a um $B_{1}$ e verificarmos se tem **outro** $B_{1}$ e, caso tivermos, precisaremos subordinar um com o outro e assim sucessivamente.

![[Binomial Inserção.svg| center | 300]]

Posto isso, o processo de inserção se propaga quantas vezes for necessário de modo que não podemos ter duas árvores binomiais de mesmo índice.


## $\texttt{Implementação.}$

A implementação em código de uma árvore binomial envolve, em um primeiro momento, a **criação de um ponteiro para o primeiro filho** juntamente de um ponteiro para os irmãos (da esquerda para direita) e, por fim, é possível que teríamos um ponteiro de cada filho para seu respectivo pai. Segue a figura abaixo:

![[Ponteiro em Árvore Binomial.svg|center|500]]

Para minimizarmos o custo total, poderíamos ter um **ponteiro para o último filho** e fazer com que os **ponteiros entre os irmãos sejam da direita para esquerda**. Feito isso, o processo de subordinação terá custo de $\mathcal{O}(1)$. Os nós também terão um campo indicando sua ordem.

![[Heap Binomial, avaliação tardia e complexidade amortizada.mp4]]

Para armazenarmos a **coleção de árvores binomiais**, podemos tanto empregar uma **lista encadeada** por meio de ponteiros entre os irmão ou, mais notadamente, entre as raízes de cada árvore binomial. Por outro lado, podemos também empregar um **vetor** em que cada posição armazenaria uma árvore binomial de ordem distinta.

Suponha que desejamos inserir a chave "33" na estrutura abaixo.

![[Lista Encadeada Heap Binomial.svg|center|700]]

O número de árvores é da ordem $\log n$ e podemos calcular de forma simples. Se considerarmos que ...

O custo da inserção é da ordem $\mathcal{O}(\log n)$ também.

Para encontrar o mínimo, basta criarmos um campo para armazenar o mínimo e, a cada raiz nova de uma árvore binomial, comparamos e trocamos valor mínimo armazenado se necessário. A complexidade nesse caso é de ordem $\mathcal{O}(1)$.

Para realizar a remoção do mínimo em uma heap binomial, pegamos a lista encadeada inicial e removemos o mínimo que encontramos na etapa anterior. Feito isso, a remoção anterior irá expandir a árvore em outras $B_{i}$ de modo que teremos que **distribuir** estas nas outras árvores da coleção de árvores binomiais. Aqui vai um exemplo:

*Vamos continuar, mas verei outra matéria por enquanto..*
