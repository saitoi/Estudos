---
aliases:
  - doubly
  - duplamente
  - lista_dupla
tags:
  - ED
date: 2023-07-20
time: 19:45
---

# Lista Duplamente Encadeada

> $\textit{Definição.}$ Estrutura de dados linear cujos elementos básicos (nós) possuem um ponteiro para o próximo elemento (sucessor) e um ponteiro para o anterior (antecessor).

A principal diferença entre listas duplamente encadeadas e simplesmente encadeadas é a presença de um ponteiro para o nó anterior.

## $\texttt{Estrutura.}$

Aqui está a estrutura básica que representa cada nó da lista duplamente encadeada.

```c
typedef struct node {
	int data;
	struct node *anterior;
	struct node *proximo;
}
```

A estrutura básica do nó de uma lista duplamente encadeada  contém a `data`, identificador numérico de cada nó, juntamente dos ponteiros `*anterior` e `*proximo` que apontam para o elemento anterior e próximo da lista, respectivamente.

## $\texttt{Inserção.}$

### $\texttt{Inserção no início.}$



### $\texttt{Inserção no fim.}$



### $\texttt{Inserção ordenada.}$

O algoritmo de inserção de um nó em uma lista duplamente encadeada e ordenada com nó cabeça está descrito na prova de 2016. Aqui está

![[Prova 2016#1. Algoritmos em C de busca e inserção de um nó em uma lista duplamente encadeada, ordenada com nó cabeça. Em um primeiro momento, aqui está o algoritmo de inserção na lista duplamente encadeada.|prova2016]]
![[Prova 2016#$ qquad$]]

No entanto, se desejamos recriar um algoritmo de inserção que insira os valores em ordem crescente na lista, poderíamos fazer a função de inserção da seguinte forma

```c
void inserirOrdenado(No* cabeca, int data) {
	No *novoNo = criarNo(data);
	No *auxiliar = cabeca->proximo;
	
	while (data > auxiliar->data && auxiliar != NULL)
		auxiliar = auxiliar->proximo;
	
	if (auxiliar == NULL) {
		No *ultimoNo = cabeca;
		while (cabeca->proximo != NULL) ultimoNo = ultimoNo->proximo;
		novoNo->proximo = NULL;
		novoNo->anterior = ultimoNo;
		ultimoNo->proximo = novoNo;
	} else {
		novoNo->proximo = auxiliar;
		novoNo->anterior = auxiliar->anterior;
		auxiliar->anterior->proximo = novoNo;
		auxiliar->anterior = novoNo;
	}
}
```

$\textbf{Explicação.}$ A função `inserirCrescente()` realiza a inserção de um nó

## $\texttt{Remover chave.}$

O algoritmo de remoção de uma chave $x$ está especificado na prova de 2018.

![[Provas#1. Algoritmo em C de remoção de uma chave $x$ de uma lista encadeada com nó cabeça. 9aa38b|prova2018]]
