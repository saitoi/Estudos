---
alias: shell
tags: C/ordem Cpp/ordem
date: 2023-07-25
time: 09:12
---

# Shell Sort

> $\textit{Definição.}$ Algoritmo baseado no [[Paradigmas#^ddb8ae| paradigma da divisão e conquista]] que envolve a divisão da lista de elementos a ser ordenada em subgrupos menores e, em seguida, aplicando o algoritmo da inserção a cada subgrupo. 

**Complexidade**: Não é possível determinar a complexidade do shell sort, pois depende da sequência de "gap".

> [!example] Exemplo de funcionamento do Shell Sort
> ![[shell_sort.gif|300]]

## Código usando vetores

```c
void shell_sort(int arr[], int n) {
int gap, i, j, temp;

	// Definindo a sequência de incrementos (gaps)
	for (gap = n / 2; gap > 0; gap /= 2) {
		// Aplicando o algoritmo de inserção em cada subgrupo
		for (i = gap; i < n; i++) {
			temp = arr[i];
			for (j = i; j >= gap && arr[j - gap] > temp; j -= gap) {
				arr[j] = arr[j - gap];
			}
			arr[j] = temp; 
		} 
	}
}
```
