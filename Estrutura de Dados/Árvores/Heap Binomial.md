---
aliases:
  - heap_binomial
  - complex_amortizada
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
## $\texttt{Implementação.}$

A implementação em código de uma árvore binomial envolve, em um primeiro momento, a **criação de um ponteiro para o primeiro filho** juntamente de um ponteiro para os irmãos (da esquerda para direita) e, por fim, é possível que teríamos um ponteiro de cada filho para seu respectivo pai. Segue a figura abaixo:

![[Ponteiro em Árvore Binomial.svg|center|500]]

Para minimizarmos o custo total, poderíamos ter um **ponteiro para o último filho** e fazer com que os **ponteiros entre os irmãos sejam da direita para esquerda**. Feito isso, o processo de subordinação terá custo de $\mathcal{O}(1)$. Os nós também terão um campo indicando sua ordem.

Para armazenarmos a **coleção de árvores binomiais**, podemos tanto empregar uma **lista encadeada** por meio de ponteiros entre os irmão ou, mais notadamente, entre as raízes de cada árvore binomial. Por outro lado, podemos também empregar um **vetor** em que cada posição armazenaria uma árvore binomial de ordem distinta.

Suponha que desejamos inserir a chave "33" na estrutura abaixo.

![[Lista Encadeada Heap Binomial.svg|center|700]]

Em uma heap binomial, podemos afirmar que o número total de nós deve ser maior ou igual ao número de nós em uma árvore binomial qualquer $2i$ dessa heap. Desse modo, podemos expressar essa propriedade da seguinte forma:
$$
n\geq 2i
$$
Em que,
- $n:$ $\#$ de nós da heap binária.
- $i:$ Ordem de uma árvore binomial qualquer.

Feito isso, extraímos que,
$$
i\leq \log n
$$
Portanto, o número máximos de árvores que se pode ter em uma heap binomial é $\log n$, considerando que as árvores tem ordens distintas. Desse modo, no pior caso, o custo da inserção é de $\mathcal{O}(\log n)$, isto é, se subordinarmos cada uma das árvores da heap binomial.

## $\texttt{Inserção.}$

O processo de inserção em uma heap binomial é relativamente simples. Basta inserirmos um novo nó que será correspondente a um $B_{1}$ e verificarmos se tem **outro** $B_{1}$ e, caso tivermos, precisaremos subordinar um com o outro e assim sucessivamente.

![[Binomial Inserção.svg| center | 300]]

Posto isso, o processo de inserção se propaga quantas vezes for necessário de modo que não podemos ter duas árvores binomiais de mesmo índice.

## $\texttt{Achar o mínimo.}$

Para encontrar o mínimo, basta criarmos um campo para armazenar o mínimo e, a cada raiz nova de uma árvore binomial, comparamos e trocamos valor mínimo armazenado se necessário. A complexidade nesse caso é de ordem $\mathcal{O}(1)$.

## $\texttt{Remover o Mínimo.}$

Para realizar a remoção do mínimo em uma heap binomial, pegamos a lista encadeada inicial e removemos o mínimo que encontramos na etapa anterior. Feito isso, a remoção anterior irá expandir a árvore em outras $B_{i}$ de modo que teremos que **distribuir** estas nas outras árvores da coleção de árvores binomiais. Aqui vai um exemplo:

![[Heap Binomial Remoção.svg|center|500]]

O custo da remoção é da ordem de $\mathcal{O}(\log n)$, 

**Comparação dos custos entre** [[Estrutura de Dados/Árvores/Heap Binária|heap binárias]] e heap binomiais:

|                   | Heap Binária             | Heap Binomial |
| ----------------- | ------------------------ | ------------- |
| **Insere**        | $\mathcal{\; O}(\log n)$ |    $\mathcal{O}(\log n)$         |
| **Remove Mínimo** | $\mathcal{\; O}(\log n)$ |    $\mathcal{O}(\log n)$           |
| **Achar Mínimo**  | $\mathcal{O}(1)$         |   $\mathcal{\; O}(1)$            |
| **Merge**         | $\mathcal{O}(n)$         |   $\mathcal{O}(n)$            |

## $\texttt{Algoritmo de Descer.}$

Um dos códigos mais cobrados da prova envolvendo **heap binomiais** diz respeito ao algoritmo de descer que possui complexidade $\mathcal{O}(n)$. Aqui está o código referente a esse processo:

De antemão, aqui está a estrutura do `node` empregado no algoritmo mais abaixo:

```c
struct Node {
    int chave;
    Node* pai;
    Node* filho;
    Node* irmao;
};

void descerBinomial(Node* pt) {
    if (pt == nullptr) {
        return;
    }

    Node* aux = pt->filho;
    Node* noMinimo = aux;

    while (aux != nullptr) {
        if (aux->chave < noMinimo->chave) {
            noMinimo = aux;
        }
        aux = aux->irmao;
    }

    if (noMinimo != pt->filho && noMinimo->chave < pt->chave) {
        int temp = noMinimo->chave;
        noMinimo->chave = pt->chave;
        pt->chave = temp;
        descerBinomial(noMinimo);
    }
}

```

**Explicação**: Precisamos de uma descrição mais detalhada para os campos de cada nó. Nesse sentido, vamos começar descrevendo os **ponteiros**:

- `pai`: Aponta para o único pai do respectivo nó atual.
- `filho`: Aponta para o **primeiro filho** do nó atual.
- `irmao`: Aponta para o irmão da **esquerda para direita** do nó atual.



**Complexidade**: 

## $\texttt{Complexidade Amortizada.}$

> $\textit{Definição.}$ *Conceito de estrutura de dados que se concentra na média do custo de operações ao longo  de uma sequência de operações, em oposição ao custo de uma operação individual.*

Nesse sentido, é possível demonstrarmos que o custo de $n$ inserções em uma árvore binomial é de complexidade $\mathcal{O}(n)$ ao invés de custar $\mathcal{O}(n \log n)$. Podemos demonstrar isso por meio do conceito das "moedinhas":

Suponha que para cada nó novo que criamos, damos uma moedinha para o nó de modo que o custo dessa operação juntamente do de criação seja $\mathcal{O}(2)$. Ademais, considere que para cada subordinação a moeda da árvore que será subordinada irá "pagar" pela subordinação e, assim, teremos:

*Imagem de um nó sendo inserido com moedinha.*

 

## $\texttt{Avaliação Tardia.}$

> $\textit{Definição.}$ *Refere-se à técnica de adiar a realização de alguma tarefa até o momento em que seu resultado for necessário. No contexto de heap binomiais, iremos permitir que hajam mais de uma heap da mesma ordem, sem unirmos as duas.*

As outras operações permanecem as mesmas, no entanto a história é outra para a remoção do mínimo, uma vez que teremos que percorrer o conjunto inteiro de nós, ou seja, teria um custo de $\mathcal{O}(n)$.

Ao remover o mínimo, teremos que subordinar cada uma das árvores e por tudo em seu devido lugar (tudo que deveríamos ter feito antes). No entanto, após remover o mínimo, não precisaremos redistribuir as árvores binomiais resultantes e apenas "deixamos" elas lá.

O custo total da remoção do mínimo é de $\mathcal{O}(\log n)$ para arrumar e um pouco mais para remover o mínimo em si.
