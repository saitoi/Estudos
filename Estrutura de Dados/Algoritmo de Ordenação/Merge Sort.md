---
alias: merge
tags: C/ordem Cpp/ordem
date: 2023-07-22
time: 15:45
---

# Merge Sort

> $\textit{Definição.}$ Algoritmo baseado no [[Paradigmas#^ddb8ae| paradigma da divisão e conquista]] que consiste em dividir a lista desordenada em duas metades, recursivamente ordenando cada metade e, por fim, combina as partes ordenadas para obter a lista final.

> [!example] Exemplo de funcionamento do Merge Sort
> ![[merge_sort.gif | 400]]

**Complexidade**: A complexidade do Merge Sort é $O(n\log(n))$ pois ele divide a lista em componentes menores, realiza a ordenação recursivamente dessas partes e, em seguida, combina elas de forma ordenada para formar a lista final.

## Código usando vetores

```c
// Função para mesclar duas sublistas ordenadas
void merge(int arr[], int left, int middle, int right) {
	int i, j, k;
	int n1 = middle - left + 1;
	int n2 = right - middle;
	
	// Cria arrays temporários para armazenar as sublistas
	int leftArr[n1], rightArr[n2];
	
	// Copia os elementos para os arrays temporários
	for (i = 0; i < n1; i++)
		leftArr[i] = arr[left + i];
	for (j = 0; j < n2; j++)
		rightArr[j] = arr[middle + 1 + j];
		
	// Mescla as duas sublistas ordenadas em uma única lista ordenada
	i = 0;
	j = 0;
	k = left;
	while (i < n1 && j < n2) {
		if (leftArr[i] <= rightArr[j]) {
			arr[k] = leftArr[i];
			i++; 
		} else {
			arr[k] = rightArr[j];
			j++; 
		}
		k++; 
	} 
	
	// Copia os elementos restantes, se houver, de ambas as sublistas
	while (i < n1) {
		arr[k] = leftArr[i];
		i++;
		k++; 
	} 
	
	while (j < n2) {
		arr[k] = rightArr[j];
		j++;
		k++;
	} 
} 

// Função principal do Merge Sort
void mergeSort(int arr[], int left, int right) {
	if (left < right) {
		int middle = left + (right - left) / 2;
		
		// Ordena a primeira metade
		mergeSort(arr, left, middle);
		
		// Ordena a segunda metade
		mergeSort(arr, middle + 1, right);
		
		// Mescla as duas metades ordenadas
		merge(arr, left, middle, right); 
	}
}
```

## Complexidade

A complexidade do Merge Sort é definida como $\mathcal{O}(n)=n\log n$, de modo que sua representação em relação de recorrência traduz para:
$$
\text{T}(n)=
\begin{cases}
2\cdot\text{T}(n/2)+n,\quad n>1 \\
1\qquad\qquad\quad\;\;,\quad n=1 \\
\end{cases}
$$
Ao resolvê-la, obtemos: $\text{T}=n+n\log n$. Como constantes aditivas não são consideradas na determinação da complexidade, nos resta $\underline{n\log n}$.