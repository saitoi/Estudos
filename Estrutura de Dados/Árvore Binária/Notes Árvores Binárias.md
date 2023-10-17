---
aliases: 
tags:
  - ED/árvores
date: 2023-09-19
time: 13:11
complete:
---

# Notes Árvores Binárias

Árvore binária é balanceada se $\forall\; \textit{no r}$, com subárvore $T_{r}$ de raiz $r$ vale 

$$
h(T_{r})=\mathcal{O}(\log \lvert T_{r} \rvert )
$$

Uma árvore binária de busca $T$ é $\textup{AVL}$ se para todo $u$ de $T$ com subárvore $T_{r}^{E}$ e $T_{r}^{D}$ temos

$$
\lvert h(T_{e}^{E})-h(T_{r}^{D}) \rvert \leq 1
$$

A regulagem de um nó $r$ é $h(T_{r}^{E})-h(T_{r}^{D})$. Uma árvore é $\textup{AVL}$ se

$$
\forall\; \textit{no},\lvert \textit{regulagem do nó} \rvert\leq 1
$$

