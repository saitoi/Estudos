---
alias: notation_O
tags: ED
date: 2023-08-25
time: 15:54
---

# Notação $\mathcal{O}$

> $\textit{Definição.}$ Notação empregada para descrever a [[Complexidade|complexidade]] de algoritmos ou funções, isto é, exprimindo o limite de crescimento em função do tempo ou espaço.

**Descrição.** Suponha que tenhamos uma função $f(n)$ em que $n$ simboliza o tamanho da entrada. Se pudermos afirmar que $f(n)$ cresce na mesma taxa ou mais devagar que $g(n)$, então $f(n)$ é $\mathcal{O}(g(n))$. Entretanto, formalmente temos:

Sejam $f,h$ funções reais positivas de variável inteira $n$. Diz-se que $f$ é $\mathcal{O}(h)$, escrevendo-se $f=\mathcal{O}(h)$, quando tivermos uma constante $c>0$ e um valor inteiro $n_0$, tal que
$$
n>n_0\implies f(n)\leq c\cdot h(n)
$$
Posto isso, a função $h$ atua como um limite superior para valores assintóticos de $f$. Aqui estão alguns exemplos:
$$
\begin{align*}
&f=n^2-1\implies f=\mathcal{O}(n^3) \\
&f=403\implies f=\mathcal{O}(1) \\
&f=5+2\cdot\log n+3\cdot\log^2n\implies f=\mathcal{O}(n)\\
&f=5\cdot2^n+5\cdot n^{10}\implies f=\mathcal{O}(2^n) \\
\end{align*}
$$
Considere também as seguintes propriedades.
Sejam $g,h$ funções reais positivas e $k$ uma constante. Então

1. $\mathcal{O}(g+h)=\mathcal{O}(g)+\mathcal{O}(h)$
2. $\mathcal{O}(k\cdot g)=k\cdot \mathcal{O}(g)=\mathcal{O}(g)$
