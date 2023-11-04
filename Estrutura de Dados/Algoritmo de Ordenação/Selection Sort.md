---
aliases:
  - selection
tags:
  - ED/Ordenação
  - C
date: 2023-07-22
time: 15:35
---

# Selection Sort

> $\textit{Definição.}$ Algoritmo simples, também fundamentado na [[Paradigmas#^3d3eca|comparação e troca]], que percorre a lista de elementos a serem ordenados e coloca-os na posição correta na lista já ordenada a sua esquerda.

**Complexidade**: A complexidade do Selection Sort é $O(n^2)$ pois a lista é percorrida duas vezes, isto é, dois comandos de repetição `for`.

> [!example] Exemplo de funcionamento do Selection Sort
> ![[selection_sort.gif | 300]]

## $\texttt{Pseudocódigo.}$

```c
vazio selectionSort(int *arr, int tamanho)
	para i de 0 até tamanho-1
		int idx = i
		para j de i+1 até tamanho
			se arr[j] > arr[i]
				idx = j
		troca(arr[idx], arr[i])
```

$\textbf{Explicação.}$ O algoritmo do Selection Sort consiste percorrer a estrutura de dados, a princípio desordenada, e identificar o menor elemento. Ao identificá-lo, trocamos este com o primeiro e assim sucessivamente. Para que isso ocorra, criamos a variável `idx` que armazena o índice do menor elemento do vetor atual. Como havia dito, trocamos esse o elemento nesse índice `arr[idx]` com o da posição desejada `arr[i]`.

## $\texttt{Código em C.}$

```c
void selection_sort(int arr[], int n) {
	int i, j, idx_min;
	for (i = 0; i < n-1; ++i) {
		idx_min = i;
		for (j = i+1; j < n; ++j)
			if (arr[j] < arr[idx_min]) {
				idx_min = j;
			}
		int temp = arr[idx_min];
		arr[idx_min] = arr[i];
		arr[i] = temp;
	}
}
```

## $\texttt{Código sem usar indexo.}$

```c
void selection_sort(int arr[], int n) {
	int i = 0, j;
	for ( ; i < n-1; ++i)
		for ( j = i+1; j < n; ++j)
			if (arr[j] < arr[i]) {
				int temp = arr[i];
				arr[i] = arr[j];
				arr[j] = arr[i];
			}
}
```

## Complexidade

