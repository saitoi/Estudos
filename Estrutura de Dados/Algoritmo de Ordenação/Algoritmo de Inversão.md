---
aliases:
  - inversion
tags:
  - ED/Ordenação
date: 2023-08-22
time: 16:13
---

# Algoritmo de Inversão

> $\textit{Definição.}$ Algoritmo simples de ordenação em que a sequência original se encontra em ordem decrescente.

### $\texttt{Algoritmo de Inversão.}$

$$
\begin{flalign}
&\textit{para i de }\text{0}\textit{ até \lfloor}n/2\rfloor:&& \\
&\textit{\qquad temp}\leftarrow\textit{S}\text{[}i\text{]}&& \\
&\textit{\qquad S}\text{[}i\text{]}\leftarrow\textit{S}\text{[}n-i+1\text{]}&& \\
&\textit{\qquad S}\text{[}n-i+1\text{]}\leftarrow\textit{temp}&& \\
&\textit{\qquad fim.}
\end{flalign}
$$

1. Notação $\lfloor x\rfloor$ indica o $\textit{piso}$ de $x$, isto é, o maior inteiro menor ou igual a $x$.
2. Analogamente, $\lceil x \rceil$ representa o teto de $x$, ou seja, o menor inteiro maior ou igual a $x$.

## Complexidade

A complexidade do algoritmo de inversão corresponde à quantidade de execuções da operação dominante, isto é, a troca de elementos ($3\text{ instruções}$). Portanto, a complexidade do processo é $\mathcal{O}(n)=\lfloor n/2\rfloor$ para $n>1$.