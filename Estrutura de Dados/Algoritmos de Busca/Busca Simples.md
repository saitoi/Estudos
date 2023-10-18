---
alias: busca_simples
tags: C/search
date: 2023-07-20
time: 17:26
---
,
# Busca Simples

> $\textit{Def. Algoritmos de busca.}$ Conjunto de instruções ou procedimentos que tem como objetivo encontrar uma determinada informação em uma estrutura de dados.

>$\textit{Def. Busca simples.}$ Percorre sequencialmente os elementos de uma estrutura de dados tal como um array/lista ([[Paradigmas#^3d3eca| paradigma da comparação e troca]]). Possuindo complexidade: $O(n^2)$.

- **Ex.** Procurando qual índice `i` da lista de tamanho `size` corresponde à `chave`.
```c
for (int i = 0; i < size; ++i) {
	if (arr[i] == chave)
		return i;
}
```
