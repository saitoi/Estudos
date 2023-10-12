---
alias: insertion
tags: C/ordem Cpp/ordem
date: 2023-07-21
time: 16:48
---

# Insertion Sort

> $\textit{Definição.}$ Algoritmo simples baseado na [[Paradigmas#^3d3eca| comparação e troca]] que percorre a lista de elementos a serem ordenados e , à medida que avança, move todos os elementos maiores que a chave para sua direita e todos os menores para sua esquerda.

**Complexidade**: A complexidade do Insertion Sort é $O(n^2)$ pois, assim como o Bubble Sort, o algoritmo realiza um número significativo de comparações e movimentos de elementos para ordenar a lista.

> [!example] Exemplo de funcionamento do Insertion Sort
> ![[insertion_sort.gif | 350]]

## $\texttt{Pseudocódigo.}$

```c
insertionSort(int *arr, int tamanho)
	para i de 1 até tamanho:
		int chave = arr[i];
		para j de i enquanto (j < 0) e (chave < arr[j-1]), j--
			arr[j] = arr[j-1]
		arr[j] = chave
```


$\textbf{Explicação. }$ O algoritmo do Insertion Sort consiste em selecionar uma chave a partir do segundo elemento da lista `arr[1]` e compará-la com seus antecessores. A comparação será realizada enquanto a chave selecionada for menor que os anteriores `arr[j-1]` e for maior ou igual a zero. As duas possibilidades para a comparação são

1. **Chave menor que anteriores.** Mova todos os maiores para a direita para "fazer" espaço para chave que será inserida.
2. **Chave está na posição correta.** Não faça nada e `arr[j]` que já vale `chave`, receberá ela novamente.

## $\texttt{Código em C.}$

```c
void insertion_sort(int arr[], int n) {
	int i, j, chave;
	for (i = 0; i < n; ++i) {
		chave = arr[i];
		j = i - 1;
		
		while (j >= 0 && arr[j] >= chave) {
			arr[j + 1] = arr[j];
			j--;
		}
		arr[j + 1] = chave;
	}
}
```

## $\texttt{Versão simplificada.}$

```c
void insertionSort(int *arr, int n) {
	int chave, j;
	for(int i = 0; i < n; ++i) {
		chave = arr[i];
		for(j = i; (j > 0) && (arr[j] > chave); --j)
			arr[j+1] = arr[j];
		arr[j] = chave
	}
}
```



