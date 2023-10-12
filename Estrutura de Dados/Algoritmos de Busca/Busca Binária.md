---
aliases:
  - busca_binaria
  - binary_search
tags:
  - ⓒ/search
date: 2023-07-24
time: 02:33
---

# Busca Binária

> $\textit{Definição.}$ Divide repetidamente o conjunto de dados ao meio, verificando a metade em que se encontra o valor e descartando a outra ([[Paradigmas#^ddb8ae| paradigma da divisão e conquista]]). Possuindo complexidade: $O(\log(n))$.

> [!example] Exemplo de funcionamento da Busca Binária
> ![[busca_binaria.gif | 500]] 

## $\texttt{Pseudocódigo.}$

```c
int buscaBinariaRecursiva(int *arr, int esquerda, int direita, int valor)
	se esquerda <= direita
		int meio = esquerda + (esquerda + direita)/2
		se arr[meio] == valor
			retorna meio;
		se valor < arr[meio]
			buscaBinariaRecursiva(arr, esquerda, meio - 1, valor)
		senão
			buscaBinariaRecursiva(arr, meio + 1, direita, valor)
	senão retorna -1
```

$\textbf{Explicação. }$ O algoritmo de busca binária recursiva é útil para determinar o índice de um valor em um vetor ordenado. Seu funcionamento consiste em identificar recursivamente o elemento central em um vetor ordenado e retorná-lo quando `arr[meio] == valor`. Enquanto o índice da esquerda for menor ou igual que o da direita ```esquerda <= direita```, a função subdividirá o vetor original em seções menores e assim sucessivamente até encontrar o valor. Caso `valor` não for encontrado, nenhuma condição será atendida e o programa retornará -1.

## $\texttt{Código em C.}$

- **Busca binária clássica.** Função clássica para busca binária em uma lista `arr[]` em busca do `valor`. 

```c
	int busca_binaria(int arr[], int left, int right, int valor) {
		while (left <= right) {
			int mid = left + (right - left) / 2;    /* Encontra o índice do meio */
		
			if (arr[mid] == valor)
				return mid;        /* Retorna o índice onde o valor é encontrado */
		
			if (arr[mid] < valor)
				left = mid + 1;    /* Procura na metade direita do array */
			else 
				right = mid - 1;   /* Procura na metade esquerda do array */
		}
		return -1;                 /* Retorna -1 se o valor não for encontrado */
	}
```

- **Busca binária recursiva.** Código anterior porém otimizado para implementar recursão.

```c
	int busca_binaria_recursiva(int arr[], int left, int right, int valor) {
		if (left <= right) {
			int mid = left + (right - left)/2;                   /* Encontra o índice do meio */   
			
			if (arr[mid] == valor)
				return mid;                                          /* Retorna o índice onde o valor é encontrado */
			
			if (arr[mid] > valor)
				busca_binaria_recursiva(arr, left, mid - 1, valor);  /* Repete, ajustando os parâmetros */
			else
				busca_binaria_recursiva(arr, mid + 1, right, valor); /* "" "" */
		}
	return -1;                                               /* Retorna -1 se o valor não for encontrado */
	}
```
