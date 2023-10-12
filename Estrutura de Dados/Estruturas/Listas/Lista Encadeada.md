---
aliases:
  - chained_list
  - lista_simples
tags:
  - ED
---

# Lista Simplesmente Encadeada

> $\textit{Definição.}$ Estrutura de dados dinâmica composta por dois elementos principais: Um nó contendo dados + ponteiro para próximo nó.

Principais pontos de listas encadeadas.

1. Nós são estruturas (`struct`) identificados por um valor numérico (`data`).
2. Adição e remoção de nós é feita por meio de alocação dinâmica.
3. Ponteiro cabeça (`*cabeca`) aponta para o primeiro nó da lista.
4. Ponteiro `*tail` é opcional e armazena o endereço do último nó.

## $\texttt{Estrutura.}$

A estrutura básica da lista encadeada está representada abaixo, podendo ser implementada de duas formas também.

```c
typedef struct node {
	int data;
	struct node *proximo;
} Node;
```

1. Contem `*cabeca` e `*fim`:

```c
typedef struct lista {
	Node *cabeca;
	Node *fim;
} Lista;
```

2. Declaração do `*cabeca` na `main`.

```c
Node *cabeca = inicializar();  
```

## $\texttt{Inicializar.}$

1. Com `*cabeca` e `*tail`:

```c
void inicializar(Lista *lista) {
	lista->cabeca = NULL;
	lista->fim = NULL;
}
```

2. Com apenas `*cabeca`:

```c
void inicializar(Node **cabeca) {
	*cabeca = (Node *) malloc(sizeof(Node));
	(*cabeca)->proximo = NULL;
}
```

$\textbf{Explicação.}$ Na função `inicializar()` foi preciso empregar ponteiros para ponteiros, pois o próprio nó cabeça teve de ser modificado, isto é, tivemos que alocar um endereço de memória da estrutura `No` para ele.

![[Árvore Binária#$ texttt{Verificar erro.}$|arvore]]

## $\texttt{Criar node.}$

```c
No *criarNode(int data) {
	No *novoNo = (No *) malloc(sizeof(No));
	verificar(novoNo);
	novoNo->data = data;
	novoNo->proximo = NULL;
	return novoNo;
}
```

## $\texttt{Adicionar no início.}$

1. Com `*cabeca` e `*fim`.

```c
void inserirInicio(Lista *minhaLista, int data) {
	Node *novoNode = criarNode(data);
	verificar(novoNode);
	
	if (minhaLista->cabeca == NULL)
		minhaLista->cabeca = minhaLista->fim = novoNode;
	else {
		
	}
}
```

2. Com apenas `*cabeca`.

```c
void inserirInicio(Node *cabeca, int data) {
	Node *novoNode = (Node *) malloc(sizeof(Node));
	
	if (novoNode == NULL) {
		puts("Erro ao alocar memória");
		return;
	}
	
	novoNode->data = data;
	novoNode->proximo = cabeca->proximo;
	cabeca->proximo = novoNode;
}
```

## $\texttt{Adicionar no final.}$

1. Com `*cabeca` e `*fim`:

```c
void adicionar_node(Lista *lista) {
	Node *novo_node = (Node *) malloc(sizeof(Node));
	
	/* Verificação */
	if (novo_node == NULL) {
		puts("Erro ao alocar memória.");
		return;
	} 
	
	le_node(novo_node);
	novo_node->prox = NULL;
	
	/* Lista vazia */
	if (lista->head == NULL)
		lista->head = lista->tail = novo_node;
	/* Lista não vazia */
	else {
		lista->tail->prox = novo_node;
		lista->tail = novo_node;
	}
}
```

2. Com apenas `*head`:

```c
void adicionar_node(Node *head) {
	Novo *novoNode = (Node *) malloc(sizeof(Node));
	
	if (novoNode == NULL) {
		puts("Erro ao alocar memória.");
		return;
	}
	
	novoNode->data = data;
	novoNode->prox = NULL;
	Node *auxiliar = cabeca;
	
	while (auxiliar->proximo != NULL) auxiliar = auxiliar->proximo;
	auxiliar->proximo = novoNode;
}
```

## $\texttt{Remover do final.}$

1. Com `*cabeca` e `*tail`:

```c
void remover_node(Lista *lista) {
	
	/* Lista vazia */
	if (lista->cabeca == NULL) {
		puts("Lista vazia, não é possível remover elementos.");
		return;
	
	/* Um elemento */
	} else if (lista->cabeca->proximo == NULL) {
		free(lista->cabeca);
		lista->cabeca = lista->fim = NULL;
	
	/* Mais de um elemento */
	} else {
		No *atual = p_lista->cabeca;
		while (atual->proximo->proximo != NULL)
			atual = atual->proximo; 
		
		free(p_lista->tail);	
		p_lista->tail = atual;
		atual->prox = NULL;
	}
}
```

2. Com apenas `*cabeca:
```c
void removerFinal(Node *cabeca) {
	Node *auxiliar = cabeca;
	
	if (head == NULL) {
		puts("Lista vazia.");
		return;
	}
	while (auxiliar->proximo->proximo != NULL) {
		auxiliar = auxiliar->proximo;
	}
	free(auxiliar->proximo);
	auxiliar->proximo = NULL;
}
```

## $\texttt{Imprimir Lista.}$

1. Com `*head` e `*tail`:

```c
void imprimirLista(Lista lista) {
	
	while (lista->head != NULL) {
		printf("%d ", lista->head->data);
		lista->head = lista->head->prox;
	}
}
```

2. Com apenas `*head`:

```c
void imprimirLista(No *head) {
	
	while (atual != NULL) {
		printf("%d ", atual->data);
		atual = atual->prox; 
	} 
}
```

3. Impressão da lista ao contrário

```c
void imprimirContrarioLista(No *head) {
	if (head == NULL) return;
	
	imprimirContrarioLista(head->prox);
	
	printf("%d ", head->data);
}
```