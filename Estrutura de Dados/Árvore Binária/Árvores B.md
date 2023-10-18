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

> $\textit{Definição.}$ Árvore binária de busca regida pelo seguinte princípio: Se um nó tem $k$ chaves e não é uma folha, então ele possui $k+1$ filhos.

Em uma árvore B, todo nó $d$ possui entre $d$ e $2d$ chaves (exceto a raiz, que tem entre 1 e $2d$ chaves) de modo que $d$ representa a <ins>ordem da árvore</ins>.



Em função do método de inserção nas árvores B, todas as folhas se encontram no mesmo nível.
Toda inserção ocorre nas folhas.

Para realizarmos a remoção, temos duas possibilidades:

1. Redistribuição

Busca em uma árvore B. $\mathcal{O}(h\cdot \log d)$
