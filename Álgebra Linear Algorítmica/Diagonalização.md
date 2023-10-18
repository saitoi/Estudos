---
aliases:
  - diagonalizacao
tags:
  - ALA
date: 2023-10-16
time: 18:43
complete:
---
$\newcommand\mycolv[1]{\begin{bmatrix}#1\end{bmatrix}}$
# Diagonalização

> $\textit{Definição.}$ Refere-se à transformação de uma matriz em sua forma diagonal.

- [i] De antemão, precisamos relembrar do conceito de <ins>matriz diagonal</ins>, isto é, uma matriz quadrada em que todos os elementos fora da diagonal principal são nulos. Por exemplo, considere a matriz diagonal $A$ descrita abaixo.
$$
\begin{align}
A=\mycolv{-1 & 0 \\0 & 1}
\end{align}
$$
Quando uma matriz puder ser transformada em sua forma diagonal, diremos que ela é uma <ins>matriz diagonalizável</ins>. Por definição, uma matriz quadrada $A$ é **diagonalizável** se existe uma matriz $P$ invertível tal que
$$
P^{-1}AP=D\tag{1}
$$
Em que $D$ se refere à matriz diagonal.

Reorganizando a expressão $(1)$, encontramos a igualdade
$$
A=PDP^{-1}
$$
Essa equação é denominada de **decomposição espectral** de uma matriz.