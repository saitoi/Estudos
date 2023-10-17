---
aliases:
  - otima
tags:
  - ED/árvores
date: 2023-10-07
time: 16:50
complete:
---
# Árvore Ótima

> $\textit{Definição.}$ Árvore binária de busca cuja estrutura permite a realização de uma busca otimizada dos elementos.

- [i] Considere uma árvore binária de busca $T$ juntamente da frequência de acesso de cada nó dado pela figura abaixo.

![[Árvore Ótima.svg|450]]

A frequência de cada nó poderá ser calculada da seguinte forma <ins>se considerarmos apenas os nós não nulos</ins>
$$
(1\cdot 100)+(2\cdot 10)+(3\cdot 5)+(4\cdot 1)=169
$$
Posto isso, ao considerarmos todos os nós de uma árvore binária de busca, definimos o custo de uma árvore ótima como sendo
$$
\textup{Custo}(T)=\sum_{i=1}^{n}f_{i}\cdot l_{i}^{T}+\sum_{i=1}^{n}f_{i}'\cdot (l_{i}'-1)
$$
De modo que,
- $f_{i}$ corresponde à frequência de acesso da chave $i$.
- $l_{i}$ equivale ao nível da chave $i$ em $T$.
- $f_{i}'$ corresponde à frequência dos nós nulos.
- $l_{i}'$ equivale ao nível dos nós nulos.

