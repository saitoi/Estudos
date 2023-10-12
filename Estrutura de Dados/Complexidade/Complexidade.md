---
alias: complexity
tags: ED
date: 2023-08-22
time: 15:30
---

# Complexidade

> $\textit{Definição.}$ Refere-se à quantidade de recursos (tempo e espaço) consumidos pelo algoritmo no decorrer de sua execução, conforme o tamanho da entrada.

Usualmente, obtemos uma expressão matemática em função da entrada do algoritmo que traduza seu comportamento de tempo por meio de métodos analíticos.

> $\textit{Definição de Passos.}$ Etapas elementares que compõe a execução do algoritmo.

> $\textit{ Definição de Operação Dominante.}$ Operação básica de maior frequência durante a execução do algoritmo.

Em algoritmos destinados à ordenação de elementos de uma sequência, cada passo corresponde à comparação entre dois elementos. Por exemplo, ao considerar o algoritmo de [[Algoritmo de Inversão|inversão dos termos]] em uma sequência, a operação dominante corresponde à troca, sendo realizados $\dfrac{n}{2}$ passos ao total.

**Obs.** Simplificações necessárias.
1. Constantes aditivas e multiplicativas não são consideradas na expressão da complexidade, como por exemplo o, valor $3n$ é aproximado para $n$.
2. Termos de menor grau são desprezados, tal como $n^2+n$ equivale a $n^2$.

Descrição da noção de **complexidade de tempo**.
Seja $A$ um algoritmo, $\{E_1,\,..\,,E_m\}$ o conjunto de todas as entradas possíveis de $A$. Denote por $t_i$, o número de passos efetuados por $A$, quando a entrada for $E_i$. Definem-se:
$$
\begin{align*}
&\textit{complexidade do pior caso}=\text{max}_{E_i\in E}\,\{t_i\} \\ \\
&\textit{complexidade do melhor caso}=\text{min}_{E_i\in E}\,\{t_i\} \\ \\
&\textit{complexidade do caso médio}=\sum_{1\leq i\leq m}p_i\,t_i
\end{align*}
$$
Onde $p_i$ é a probabilidade de ocorrência da entrada $E_i$.
O termo $\textit{complexidade}$ será empregado considerando considerando a $\textit{complexidade do pior caso}$.



