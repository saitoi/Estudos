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

> $\textit{Definição.}$ Coleção de árvores binomiais de ordens distintas tais que todo nó obedece a propriedade Heap.

- [i] A **ordem** de uma árvore binomial corresponde ao número de filhos da raiz.

De antemão, precisamos definir uma árvore binomial, isto é, 

![[Árvores Binomiais|600]]
A implementação envolve a criação de ponteiros do pai para o primeiro filho e para o último filho de modo que tenhamos um ponteiro entre irmãos de uma mesma árvore.

Também sabemos que $\lvert B_{i} \rvert=2^{i}$.