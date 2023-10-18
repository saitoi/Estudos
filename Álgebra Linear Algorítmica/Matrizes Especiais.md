---
aliases:
  - especiais
  - elementar
tags:
  - ALA
date: 2023-10-03
time: 22:42
complete: false
---
$\newcommand\mycolv[1]{\begin{bmatrix}#1\end{bmatrix}}$
# Matrizes Especiais

> $\textup{Matriz Identidade.}$ *Matriz quadrada em que todos os elementos da diagonal principal são $1$ e todos os outros são nulos.*

Denotada por $I$ ou $I_{n}$ quando se trata de uma matriz $n\times n$. Aqui está um exemplo da matriz $I_{4}$
$$
\begin{align}
I_{4}=\mycolv{1 & 0 & 0 & 0 \\0 & 1 & 0 & 0 \\0 & 0 & 1 & 0 \\0 & 0 & 0 & 0}
\end{align}
$$
> $\textup{Matriz Nula.}$ 

> $\textup{Matriz Elementar.}$ *Matriz identidade que contém uma outra posição $(i,j)$ não nula e fora da diagonal.*

^3f7ad4

Denotamos uma matriz elementar cuja entrada não nula fora da diagonal está na $i$-ésima linha e $j$-ésima coluna é ocupada pelo número real $\alpha$ será denotada $L_{r,s}(\alpha)$. Por exemplo,
$$
\begin{align}
L_{1,3}(-5)=\mycolv{1 & 0 & -5 \\0 & 1 & 0 \\0 & 0 & 1}\quad \text{e}\quad L_{3,2}(9)=\mycolv{1 & 0 & 0 \\0 & 1 & 0 \\0 & 9 & 1}  
\end{align}
$$
> $\textup{Matriz Triangular.}$ *Matriz quadrada em que todos os elementos acima ou abaixo da diagonal principal são nulos, sendo divididas entre matriz triangular superior e matriz triangular inferior.*

Dizemos que uma matriz $U$ é *triangular superior* se todas as entradas abaixo da diagonal principal são nulas, isto é, se $U_{i,j}=0$ sempre que $i<j$. Analogamente, $L$ é dita uma matriz *triangular inferior* acima da diagonal principal são nulas, o que equivale dizer que $L_{i,j}=0$ quando $i>j$. Aqui estão os exemplos citados
$$
\begin{align}
U=\mycolv{a_{11} & a_{12} & a_{13} \\0 & a_{22} & a_{23} \\0 & 0 & a_{33}}\quad \text{e}\quad L=\mycolv{b_{11} & 0 & 0 \\b_{21} & b_{22} & 0 \\b_{31} & b_{32} & b_{33}}  
\end{align}
$$
> $\textup{Matriz Simétrica.}$ *Matriz quadrada de tamanho $n\times n$ em que suas entradas satisfazem $a_{i,j}=a_{j,i}$ para todo $1\leq i\leq j\leq n$. Por outro lado, uma matriz é dita antissimétrica quando $a_{i,j}=-a_{j,i}$ para todo $1\leq i\leq j\leq n$.*

Aqui está um exemplo de uma matriz simétrica e outra antissimétrica
$$
\begin{align}
\mycolv{1 & 2 & 3 \\2 & 4 & 5 \\3 & 5 & 6}\quad \text{e}\quad \mycolv{1 & 2 & 3\\ -2 & 4 & -5 \\ -3 & 5 & 6}  
\end{align}
$$



