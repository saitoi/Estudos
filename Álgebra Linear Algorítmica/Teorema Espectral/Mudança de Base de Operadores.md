---
aliases:
  - mudanca_operadores
tags:
  - ALA
date: 2023-10-03
time: 21:38
complete: false
---
$\newcommand\mycolv[1]{\begin{bmatrix}#1\end{bmatrix}}$
# Mudança de Base de Operadores

Digamos que temos a base ortonormal $\beta=\{u_{1},u_{2}\}$ sendo $T$ um operador do plano. Supondo que conhecemos $(Tu_{1})_{\beta}$ e $(Tu_{2})_{\beta}$ podemos deduzir que
$$
\begin{align}
(T)_{\beta}=\mycolv{| & | \\(Tu_{1})_{\beta} & (Tu_{2})_{\beta} \\| & |}\tag{1}
\end{align}
$$
Portanto,
$$
(Tv)_{\beta}=(T)_{\beta}(v)_{\beta}
$$
Veremos como isso se aplica a um operador autoadjunto $T$ que tem $u_{1}$ e $u_{2}$ como autovetores unitários associados aos autovalores $\lambda_{1}$ e $\lambda_{2}$.
$$
T(u_{1})=\lambda_{1}u_{1}\quad \text{e} \quad T(u_{2})=\lambda_{2}u_{2}
$$
Considerando $u_{1}$ e $u_{2}$ como os vetores unitários do plano, reescreveremos na base $\beta$,
$$
(T(u_{1}))_{\beta}(\lambda_{1},0)\quad \text{e}\quad (T(u_{2}))_{\beta}=(0,\lambda_{2})
$$
pois
$$
\lambda_{1}\cdot u_{1}=\lambda_{1}\cdot u_{1}+0\cdot u_{2}\quad \text{e}\quad \lambda_{2}\cdot u_{2}=0\cdot u_{1}+\lambda_{2}\cdot u_{2}
$$
Aplicando à expressão $(1)$ obteremos
$$
\begin{align}
(T)_{\beta}=\mycolv{| & | \\(T(u_{1}))_{\beta} & (T(u_{2}))_{\beta} \\| & |}=\mycolv{\lambda_{1} & 0\\0 & \lambda_{2}}
\end{align}
$$
