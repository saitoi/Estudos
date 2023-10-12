---
alias: bubble
tags: C/ordem Cpp/ordem
date: 2023-07-20
time: 17:27
---

# Bubble Sort

> $\textit{Definição.}$ Algoritmo simples de ordenação baseado no [[Paradigmas#^3d3eca| paradigma da comparação e troca]] em que é percorrida repetidamente a lista a ser ordenada e são comparados os pares adjacentes, trocando-os caso estiverem fora de ordem.

**Complexidade**: A complexidade do Bubble Sort é $O(n^2)$, pois no pior caso (lista invertida) é necessário percorrê-la duas vezes para ordená-la.

> [!example] Exemplo de funcionamento do Bubble Sort:
> ![[bubble_sort.gif | 500]]

## Código usando vetores

**Obs.** O número de elementos da lista é $n$, sendo passado como referência.
```c
void bubble_sort(int arr[], int n) {
	int i, j;
	for (i = 0; i < n-1; ++i) {
		for (j = 0; j < n-i-1; ++j) {
			if (arr[j] > arr[j + 1]) {    /* Troca os elementos */
				int temp = arr[j];
				arr[j] = arr[j + 1];
				arr[j + 1] = temp;
			}
		}
	}	
}
```

$\textbf{Explicação.}$ 

## Código recursivo

```c
void bubble_sort_recursivo(int arr[], int n) {
	if (n <= 1)
		return;
	
	int i, trocado = 0;
	for (i = 0; i < n-1; ++i)
		if (arr[i] > arr[i + 1]) {
			int temp = arr[i];
			arr[i] = arr[i + 1];	
			trocado = 1;
		}
	if (trocado)
		bubble_sort_recursivo(arr, n-1);
}
```

## Complexidade

