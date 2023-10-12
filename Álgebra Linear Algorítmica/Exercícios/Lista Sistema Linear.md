---
aliases:
  - sistema_linear_resolucao
tags:
  - Exercises
  - ALA
date: 2023-10-09
time: 08:56
complete:
---
$\newcommand\mycolv[1]{\begin{bmatrix}#1\end{bmatrix}}$
### Nome: Pedro Henrique Honorio Saito

### DRE: 122149392

# Lista Sistema Linear

1. Para cada uma das questões abaixo, devemos identificar as matrizes $L$ e $U$, isto é, os tipos de matrizes elementares que compõe $L$ e a matriz resultante $U$ após a eliminação gaussiana.
$$
(a)\begin{cases}
x_{1}+x_{2}+2x_{3}&=8 \\ \\
-x_{1}-2x_{2}+3x_{3}&=1 \\ \\
3x_{1}-7x_{2}+4x_{3}&=10
\end{cases}
$$
Partindo da primeira linha, podemos multiplicar a matriz original pela elementar $L_{21}(1)$ com o intuito de eliminar o primeiro termo $x_{1}$. Teremos,
$$
\begin{cases}
x_{1}+x_{2}+2x_{3}&=8 \\ \\
-x_{2}+5x_{3}&=9 \\ \\
3x_{1}-7x_{2}+4x_{3}&=10
\end{cases}
$$
Repetindo o processo para a terceira equação, teríamos que multiplicar a última expressão por $L_{31}(-3)$ e somá-las.
$$
\begin{cases}
x_{1}+x_{2}+2x_{3}&=8 \\ \\
-x_{2}+5x_{3}&=9 \\ \\
-10x_{2}-2x_{3}&=10
\end{cases}
$$
Para concluirmos, devemos realizar o produto com a matriz elementar $L_{32}(-10)$ e obteríamos:
$$
\begin{cases}
x_{1}+x_{2}+2x_{3}&=8 \\ \\
-x_{2}+5x_{3}&=9 \\ \\
-52x_{3}&=-80
\end{cases}
$$
