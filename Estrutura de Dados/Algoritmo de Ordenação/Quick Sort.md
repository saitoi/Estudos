---
alias: quick
tags: C
date: 2023-07-26
time: 20:50
---

# Quick Sort

> $\textit{Definição.}$ Algoritmo de ordenação baseado no [[Paradigmas#^ddb8ae|paradigma de divisão e conquista]] em que escolhemos o elemento pivô e classificamos os outros em menor ou maior em relação a ele. Após aplicar o processo recursivamente a todas submatrizes, juntamos e obtemos o vetor ordenado.

> [!example] Exemplo de funcionamento do Quick Sort
> ![[quick_sort.gif | 350]]

## $\texttt{Pseudocódigo.}$

```c
vazio troca(int *a, int *b)
	int temp = *a
	*a = *b
	*b = temp

int particiona(int *arr, int inicio, int fim)
	int pivo = arr[fim]
	int i = inicio-1
	para j de inicio até fim
		se (arr[j] <= pivo)
			++i
			troca(arr[i], arr[j])
	troca(arr[i+1], arr[fim])
	retorna (i+1)

vazio quickSort(int *arr, int inicio, int fim)
	se (fim > inicio)
		int pivo = particiona(arr, inicio, fim)
		quickSort(arr, inicio, pivo-1)
		quickSort(arr, pivo+1, fim)
```

$\textbf{Explicação.}$  A função `quickSort` realiza a ordenação de elementos por meio da seleção recursiva de um pivô, elemento de referência para a subdividir a estrutura de dados entre dados maiores e menores em relação a ele.

Inicialmente, verificamos se o índice do `fim` da lista é maior que o índice do `inicio`. Se a condição for verdadeira, temos que ordenar a lista

## $\texttt{Código em C.}$

```c
// Função para trocar dois elementos do array
void swap(int* a, int* b) {
	int temp = *a;
	*a = *b;
	*b = temp;
}

// Função que coloca o pivô na posição correta no array
int partition(int arr[], int low, int high) {
	int pivot = arr[high]; // escolha o elemento mais à direita como pivô
	int i = (low - 1);     // Índice do menor elemento
	
	for (int j = low; j < high; j++) {
	// Se o elemento atual é menor ou igual ao pivô
		if (arr[j] <= pivot) {
			i++; // incrementa o índice do menor elemento
			swap(&arr[i], &arr[j]);
		}
	}
	swap(&arr[i + 1], &arr[high]);
	return (i + 1);
}

// Função recursiva para ordenar o array usando o Quick Sort
void quickSort(int arr[], int low, int high) {
	if (low < high) {
	// Obtem o índice do pivô
	int pi = partition(arr, low, high);
	
	// Ordena os elementos separadamente antes e depois do pivô
	quickSort(arr, low, pi - 1);
	quickSort(arr, pi + 1, high); 
	}
}
```

## Complexidade

