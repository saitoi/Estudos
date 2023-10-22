---
aliases:
  - heap
tags:
  - ED/Árvores
date: 2023-10-19
time: 13:09
complete:
---
# Heap Binária

> $\textit{Definição.}$ Árvore binária completa (não é de busca) em que os nós do último 

`FESQ = (p+1)/2`
`F`

## $\texttt{Inicialiazação.}$

```c
init()
	tam = TAM
	H = aloca()
	nelem = 0
```

## $\texttt{Subir.}$

Função recursiva para subir na heap binária.

```c
subir(H, pos)
	se pos > 0
		pai = PAI(pos)
		se H[pos] < H[pai]
			x = H[pos]
			H[pos] = H[pai]
			H[pai] = x
			subir(H, pai)
```

Função fechada para subir na heap binária.

```c
subir(H, pos)
	se pos != 0
		x = H[pos]
		enquanto (pos != 0 e H[PAI(pos)] < x)
			H[pos] = H[PAI(pos)]
			pos = PAI(pos)
		H[pos] = x
```

Complexidade: $\mathcal{O}(n\log n)$

## $\texttt{Descer.}$

```c
desce(H, nelem, pos)
	posFilho = FESQ(pos)
	se posFilho < nelem
		menorFilho = H[posFilho]
		se (posFilho + 1) < nelem
			se H[posFilho] < menorFilho
				posFilho++
				menorFilho = H[posFilho]
			se H[pos] > menorFilho
				H[posFilho] = H[pos]
				H[pos] = menorFilho
				desce(H, nelem, posFilho)
```

## $\texttt{Inserção.}$

```c
insere(H, nelem, tam, x)
	se nelem == tam
		overflow()
	se nelem < tam
		H[nelem] = x
		subir(H, nelem)
		nelem++
```

- [i] O algoritmo do `Heap Sort` para a transformação de um vetor qualquer em Heap binária consiste em aplicar a função `subir(V,i)` para cada elemento do vetor desordenado como abaixo.

```c
para i de 1 até nelem-1
	subir(V, i)
```

Complexidade: $\mathcal{O}(n \log n)$

Podemos fazer de uma forma melhor:

```c
para i de nelem-1 até 0
	descer(i)
```

Complexidade: $\mathcal{O}(n)$

## $\texttt{Remover menor.}$

```c
removeMenor(H, nelem)
	nelem--
	H[0] = H[nelem]
	desce(H, nelem, 0)
```

## $\texttt{Heap Sort.}$

```c
heapSort(V, nelem)
	criaHeap(V, nelem)
	enquanto (nelem > 1)
		nelem--
		tmp = V[0]
		v[0] = v[nelem]
		desce(V, nelem, 0)
```

Complexidade: $\mathcal{O(n \log n)}$, a função `desce(V, nelem, 0)` possui complexidade $\mathcal{\log n}$.
