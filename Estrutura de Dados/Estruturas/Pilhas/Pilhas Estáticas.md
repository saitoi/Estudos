---
aliases:
  - pile_static
tags:
  - ED
---

# Pilhas Estáticas

> $\textit{Definição.}$ Estrutura de dados linear que segue o princípio Last-In-First-Out (LIFO), isto é, o último termo é o primeiro a ser removido.

Principais pontos de pilhas estáticas.

1. 

## $\texttt{Estrutura.}$

```c
typedef struct pilha {
	int data[MAX_TAM];
	int topo;
} Pilha;
```

## $\texttt{Inicializar.}$

```c
void inicializar(Pilha *pilha) {
	pilha->topo = -1;    /* -1 indica que a pilha está vazia */
}
```

### Verificar pilha vazia:

```c
int estaVazia(Pilha *pilha) {
	return (pilha->topo == -1);
}
```

### Verificar pilha cheia:

```c
int estaCheia(Pilha *pilha) {
	return (pilha->topo == MAX_TAM - 1);
}
```

### Empilhar:

```c
void empilhar(Pilha *pilha, int valor) {
	if (estaCheia(*pilha)) {
		puts("Pilha está cheia, não é possível empilhar.");
		return;
	}
	
	(pilha->topo)++;
	pilha->data[pilha->topo] = valor;
}
```

### Desempilhar:

```c
void desempilhar(Pilha *pilha) {
	if (estaVazia(*pilha)) {
		puts("Pilha está vazia, não é possível remover elementos.")
		return;
	}
	
	int removido = pilha->data[pilha->topo];
	(pilha->topo)--;
	printf("%d foi removido com sucesso.\n", removido);
}
```

### Imprimir a pilha:

```c
void imprimir_pilha(Pilha pilha) {
	if (estaVazia(*pilha)) {
		puts("Pilha está vazia, não é possível imprimí-la.");
		return;
	}
	
	puts("")
	for (int i = pilha.topo; i > -1; --i) {
		
	}
}
```

> [!example] Empilhamento e Desempilhamento
> Suponha que temos a pilha $\text{A1}$ com 4 valores não designados, dispostos da seguinte forma:
> 
> ```tikz
> \begin{document}
> \begin{tikzpicture}[scale=1]
>  % Definir o estilo do retângulo
>  \tikzstyle{rect} = [draw, rectangle, minimum width=1cm, minimum height=0.75cm]
>
>  % Desenhar os retângulos e rótulos
 > \node[rect] (a1-1) at (0,0.75) {Valor 1};
 > \node[rect] (a1-2) at (0,0) {Valor 2};
>  \node[rect] (a1-3) at (0,-0.75) {Valor 3};
 > \node[rect] (a1-4) at (0,-1.5) {Valor 4};
>
>  % Rótulo "A1"
>  \node[above] at (a1-1.north) {A1};
>\end{tikzpicture}
>\end{document}
>
> ```
>
> Se utilizarmos a função `pop()` sobre os 4 elementos de $\text{A1}$ e atribuirmos a uma pilha vazia $\text{A2}$ por meio do comando `push()`, obteremos a seguinte configuração:
> <span class='centerImg'> ![[pilha_A2.png|290]] </span>    
> Portanto, podemos observar que os elementos da pilha $\text{A1}$ estão dispostos de forma invertida em $\text{A2}$, visto que ao utilizar o comando `pop()`, estamos removendo os valores do topo e inserindo-os "no fundo" em $\text{A2}$ diretamente.

