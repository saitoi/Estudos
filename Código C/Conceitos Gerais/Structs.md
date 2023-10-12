---
alias: estruturas
tag: ⓒ
---

# Structs

> $\textit{Definição.}$ Conjunto de uma ou mais [[Código C/Conceitos Gerais/Variáveis]] de diferentes tipos (ou não), agrupadas sob um único nome, facilitando a manipulação dos dados armazenados dentro dela.

Acesso de campos da estrutura:
- Ponteiros para *structs* usam a notação "seta" `->`
	- **Ex.** `NomePont->campo1`.
- Structs simples usam a notação "ponto" `.`
	- **Ex.** `NomeStruct.campo2`.

## Declarações para estruturas

- Tipo `struct` atrelado ao nome:
```c
struct Node {
	int data;
	struct Node *prox;
};
```

- Comando `typedef` com nome:
```c
typedef struct node {
	int data;
	struct node *prox;
} Node;
```

- Comando `typedef` sem nome:
```c
typedef struct {
	int data;
	/* Não é possível declarar ponteiros */
} Node;
```

- Múltiplas estruturas:
```c
struct Node {
	int data;
	struct Node *prox;
} node1, node2, node3;    /* node1, node2, ... são estruturas */
```





