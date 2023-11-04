---
aliases:
  - inversion_chained_list
tags:
  - ALA
date: 2023-09-05
time: 21:48
complete: true
---
# Inversão da Lista Encadeada

> $\textit{Definição.}$ Algoritmo destinado à inversão das estruturas em uma lista encadeada, ou seja, inversão do sentido dos ponteiros.

A apresentação e explicação do algoritmo será feita em C. Assim sendo, para começarmos suponha a estrutura `Node` possuindo dois campos, `int data` referente ao conteúdo do nó e `struct node *next` para apontar para o próximo elemento da lista.

```c
typedef struct node {
	int data;
	struct node *next;
} Node;
```

Posto isso, necessitaremos de funções para a criação de um novo elemento (`Node *newNode(int data)`) e impressão da lista as quais serão descritas abaixo:

```c
Node *newNode(int data) {
	Node *newNode = (Node *) malloc(sizeof(Node));
	newNode->data = data;
	newNode->next = NULL;
	return newNode;
}
```

A função acima apenas retorna o nó recém alocado com seu conteúdo já inicializado, assim sendo alguma variável na `main` será encarregada de receber esse endereço.

```c
void imprimirLista(Node *head) {
	Node *temp = head;
	while (temp != NULL) {
		printf("%d\n", temp->data);
		temp = temp->next;
	}
}
```

A impressão da lista é uma função simples que percorre sequencialmente cada nó a partir do `head` que, por sua vez, passará a apontar para o último elemento da lista após a inversão. Por fim, o algoritmo recursivo para a inversão da lista encadeada será exibido abaixo.

```c
struct Node* reverseList(struct Node* ptr_recursive, struct Node** ptr_list) {
    if (ptr_recursive->next == NULL) {
        *ptr_list = ptr_recursive;
        return ptr_recursive;
    }
        struct Node* recursive = reverseList(ptr_recursive->next, ptr_list);
        recursive->next = ptr_recursive;
        ptr_recursive->next = NULL;
        return ptr_recursive;
}
```

**Explicação.** A função recursiva para a inversão da lista encadeada inicia com a condição `(ptr_recursive->next == NULL)` que será utilizado posteriormente para verificar se alcançamos o fim da lista e retornarmos o endereço do último nó.

Desse modo, temos a atribuição da chamada recursiva `reverseList(ptr_recursive->next, ptr_list)` ao ponteiro para nó criado `recursive`. A partir deste momento, o programa executa repetidas vezes o primeiro trecho do programa, ou seja, a condição inicial, e realiza a chamada recursiva até que `ptr_recursive->next == NULL` seja atendido.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.9]
    % Desenha o primeiro retângulo com a palavra "programa" dentro
    \draw (0, 0) rectangle (1.8, 1) node[pos=.5] {programa};
    
    % Desenha o vetor no lado de fora do primeiro retângulo
    \draw[->] (0, -0.3) -- (0, -1.5) node[midway, right] {metade};
    \node at (0, -1.75) {fim};
    
    % Desenha o segundo retângulo com a palavra "programa" dentro
    \draw (3, 0) rectangle (4.8, 1) node[pos=.5] {programa};
    
    % Desenha o vetor no lado de fora do segundo retângulo
    \draw[->] (3, -0.3) -- (3, -1.5) node[midway, right] {metade};
    \node at (3, -1.75) {fim};
    
    % Desenha o terceiro retângulo com a palavra "programa" dentro
    \draw (6, 0) rectangle (7.8, 1) node[pos=.5] {programa};
    
    % Desenha o vetor no lado de fora do terceiro retângulo
    \draw[->] (6, -0.3) -- (6, -1.5) node[midway, right] {metade};
    \node at (6, -1.75) {fim};
    
    \node (largenode) at (8.5, 0.5) {\large{...}};
    
    % Desenha o quarto retângulo com a palavra "programa" dentro
    \draw (9, 0) rectangle (10.8, 1) node[pos=.5] {programa};
    
    % Desenha o vetor no lado de fora do quarto retângulo
    \draw[->] (9, -0.3) -- (9, -1.5) node[midway, right] {condição atendida};
    \node at (9, -1.75) {fim};
    
    % Adiciona a seta do último retângulo para o penúltimo retângulo
    \draw[->] (10.8, 0.5) -- (11.8, 0.5) node[above, right] {$\;$retornando..};
\end{tikzpicture}
\end{document}
```

Assim que a condição é atendida, o endereço do último nó é retornado à variável `recursive` da penúltima execução e assim sucessivamente. Assim sendo, essa variável passa a apontar para a penúltima e o processo se repete para as demais chamadas do programa, formando uma lista encadeada invertida.