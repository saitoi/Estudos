---
aliases:
  - avl
tags:
  - ED/Árvores
date: 2023-09-21
time: 13:24
complete:
---

# Árvore AVL

> $\textit{Definição.}$ Estrutura de dados de árvore balanceada, isto é, a diferença de altura entre as subárvores esquerda e direita ($\textit{regulagem do nó}$) é mantida menor ou igual a $1$.

Chamamos uma árvore binária de balanceada  se para todo nó $r$ com subárvore $T_{r}$ vale a expressão:
$$
h(T_{r})=\mathcal{O}(\log \lvert T_{r} \rvert ).
$$
Posto isso, uma árvore binária de busca $T$ é dita **AVL** se para todo nó $r$ de $T$ com subárvores $T_{r}^{E}$ e $T_{r}^{D}$ temos que
$$
\lvert h(T_{e}^{E})-h(T_{r}^{D}) \rvert \leq 1.
$$
Dizemos que essa diferença de altura $h(T_{e}^{E})-h(T_{r}^{D})$ entre as subárvores direita e esquerda corresponde à regulagem do nó. Em uma árvore **AVL**, a regulagem do nó é menor ou igual a 1 por definição.