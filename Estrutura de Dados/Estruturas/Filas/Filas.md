---
aliases:
  - row
tags: []
---

# Filas

> $\textit{Definição.}$ Estrutura de dados linear que segue o princípio First-In-First-Out (FIFO), isto é, o primeiro elemento é o primeiro a sair.

**Obs.** Existem diferentes formas de implementar filas, iremos apresentar filas com vetores e listas encadeadas.

## Funções principais com vetor:

### Estrutura básica:

```c
typedef struct fila {
	int frente,
		tras,
		data[MAX_TAM];
} Fila;
```

### Inicializar:

```c
void inicializar(Fila *fila) {
	fila->frente = -1;
	fila->tras = -1;
}
```

### Verificar fila vazia:

```c
int estaVazia(Fila fila) {
	return (fila.frente == -1 && fila.tras == -1);
}
```

### Verificar fila cheia:

```c
int estaCheia(Fila fila) {
	return (fila.frente == (MAX_TAM - 1));
}
```

### Enfileirar:

```c
void enfileirar(Fila *fila, int valor) {
	if (estaCheia(*fila)) {
		puts("Fila está cheia, não é possível enfileirar.");
		return;
	}
	
	if (estaVazia(*fila))
		fila->frente = fila->tras = 0;	
	else
		(fila->tras)++;
	
	fila->data[fila->tras] = valor;
	printf("%d foi enfileirado com sucesso.\n", valor);
}
```

### Desenfileirar:

```c
void desinfileirar(Fila *fila) {
	if (estaVazio(*fila)) {
		puts("Fila está vazia, não é possível remover elementos.");
		return;
	}
	
	int removido = fila->data[fila->frente];
	(fila->frente)++;
	printf("Valor removido: %d.\n", removido);
}
```

### Imprimir fila:

```c
void imprimir_fila(Fila fila) {
	if (estaVazia(fila)) {
		puts("Fila está vazia, não é possível imprimir.");
	}
	printf("Fila (Frente -> Tras): ");
	for (int i = fila.frente; i <= fila.tras; ++i)
		printf("%d ", fila.data[i]);
}
```

## Funções Principais com lista encadeada

A estrutura da fila nesse formato é idêntico à [[Lista Encadeada | lista encadeada]] com a diferença nas funções de enfileirar/desenfileirar.

### Enfileirar:

```c
void enfileirar(Fila *fila, int valor) {
	Node *novo_node = (Node *) malloc(sizeof(Node));
	/* Verificação */
	if (novo_node == NULL) {
		puts("Erro ao alocar memória.");
		return;
	}
	
	novo_node->prox = NULL;
	novo_node->data = valor;
	
	if (estaVazia(*fila))
		fila->frente = fila->tras = novo_node;
	else
		
}
```

### Desenfileirar:

```c
void desenfileirar(Fila *fila) {
	
	if (estaVazia(*fila)) {
		puts("Fila está vazia, não é possível remover elementos.");
		return;
	}
	
	int removido = fila->frente->data;
	if (fila->frente->prox == NULL) {
		fila = fila->frente->prox;
	}
}
```