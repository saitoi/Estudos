---
aliases:
  - graduada
tags:
  - ED/Árvores
date: 2023-10-10
time: 14:10
complete:
---
# Árvore Graduada

> $\textit{Definição.}$ Árvore binária de busca na qual todo nó tem um posto satisfazendo as seguintes condições:

1. Posto de externo é $\cancel{0}$.
2. Posto de pai de externo é 1.
3. Se $v$ é pai de $u$, então $\text{posto}(v)=\text{posto}(u)$ ou $\text{posto}(u)+1$
4. Se $v$ é avô de $u\implies \text{posto}(v)>\text{posto}(u)$.