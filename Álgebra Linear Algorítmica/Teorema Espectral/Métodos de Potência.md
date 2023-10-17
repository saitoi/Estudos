---
aliases: 
tags:
  - ALA
date: 2023-10-17
time: 00:27
complete:
---
$\newcommand\mycolv[1]{\begin{bmatrix}#1\end{bmatrix}}$
# Métodos de Potência

> $\textit{Definição.}$ Algoritmo iterativo baseado no cálculo de potências sucessivas de um operador que, por sua vez, converge para um autovetor.

Seja $T$ um operador autoadjunto do plano, cujos autovalores não são nulos. Dado um vetor unitário $u_{0}$ qualquer, definimos a sequência $u_{0},u_{1},\dots$ recursivamente pela expressão abaixo
$$
u_{i}=\dfrac{T(u_{i-1})}{\|T(u_{i-1})\|}\tag{1}
$$
$\textup{Lema.}$ *Sejam $v_{1}$ e $v_{2}$ vetores não nulos do plano. Se $v_{1}$ é múltiplo de $v_{2}$, então as normalizações de $v_{1}$ e $v_{2}$ são iguais, a menos o sinal. Em particular, se $a>0$, as duas normalizações são iguais.*

$\textup{Lema.}$ *Se $T$ é um operador linear autoadjunto cujos autovalores não são nulos e $u_{0}$ é um vetor do plano, então*
$$
u_{i}=\dfrac{T^{i}(u_{0})}{\|T^{i}(u_{0})\|}
$$
$\textup{Demonstração.}$ Retornando à expressão $(1)$, denotaremos o inverso da norma de $T(u_{j})$ de $n_{j}$, agora substituindo na equação teremos
$$
u_{i}=n_{i-1}T(u_{i-1})\quad \text{e}\quad u_{i-1}=n_{i-2}T(u_{i-2}).
$$
Substituindo a segunda igualdade na primeira teremos
$$
u_{i}=n_{i-1}n_{i-2}T^{2}(u_{i-2}).
$$
Mas $u_{i-2}=n_{i-3}T(u_{i-3})$ de modo que
$$
u_{i}=n_{i-1}n_{i-2}T^{2}(n_{i-3}T(u_{i-3}))
$$
Repetindo esse argumento repetidas vezes, obteremos finalmente
$$
u_{i}=n_{i-1}n_{i-2}\dots n_{0}T^{i}(u_{0}).
$$
Portanto, como $n_{j}>0$, então pelo lema, $u_{i}$ é igual à normalização de $T^{i}(u_{0})$.

