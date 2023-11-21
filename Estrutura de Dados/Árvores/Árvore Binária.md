---
aliases:
  - binary_tree
  - tree
  - arvore
tags:
  - ED/Árvores
date: 2023-09-14
time: 14:05
complete:
---

# Árvore Binária

> $\textit{Definição.}$ Estrutura de dados hierárquica cujos elementos básicos são denominados nós e apontam para no máximo dois outros nós.

Empregamos algumas nomenclaturas para se referir às funcionalidades dos nós:

1. **Nó raiz.** Ponto de partida da árvore ou subárvore.
2. **Nó folha.** Não possui filhos, situados no final da árvore.
3. **Nó pai.** Nó que antecede o nó filho e aponta para o mesmo.
4. **Nó filho.** Nó que precede o nó pai, sendo apontado por este mesmo.

Cada nó possui uma chave (valor numérico) que o identifica. Eles são dispostos na árvore conforme a magnitude da chave com relação a do $\textit{nó pai}$, ou seja, se a chave do nó filho for inferior ao do $\textit{nó pai}$, ele será colocado à **esquerda** do $\textit{pai}$. Por outro lado, se a chave for superior a do $\textit{nó pai}$ ele será posicionado à **direita** desse. Aqui está um exemplo de árvore binária
```tikz
\begin{document}
\begin{tikzpicture}
  % Defina os nós da árvore binária
  \node {A}
    child {
      node {B}
      child {
        node {D}
      }
      child {
        node {E}
      }
    }
    child {
      node {C}
      child[missing] {}
      child {
        node {F}
      }
    };
\end{tikzpicture}
\end{document}
```

De modo que cada nó $A,B,\dots,F$ possui chave que o identifica na árvore.

$\textbf{Obs.}$ Em uma árvore binária normal, não há uma ordem para a inserção dos elementos ($\textit{esquerda = menor, direita = maior ou igual}$). No entanto, em uma **árvore binária de busca** (**BST**), os elementos são ordenados conforme seu identificador numérico (chave).

## $\texttt{Estrutura.}$

A declaração da estrutura que representa os nós da árvore binária está descrita abaixo:

```c
typedef struct no {
	int chave;
	struct no *esquerda;
	struct no *direita;
	int altura;
} No;
```

Estrutura simples que contém os campos `chave` (identificador inteiro) e `esquerda` com `direita` os quais armazenam os endereços dos nós apontados por cada um.

## $\texttt{Verificar erro.}$

```c
void verificar(void *estrutura) {
	if (estrutura == NULL) {
		puts("Erro ao alocar memória.");
		exit(1);
	}
}
```

## $\texttt{Adicionar nó.}$

```c
No *criarNo(int chave) {
	No *novoNo = (No *) malloc(sizeof(No));
	verificar(novoNo);
	
	novoNo->chave = chave;
	novoNo->esquerda = NULL;
	novoNo->direita = NULL;
	novoNo->altura = 1;
	return novoNo;
}
```

A função `criarNo` apenas aloca uma estrutura do tipo `No` e inicializa os campos necessários (`chave`, `esquerda` e `direita`). Posto isso, o endereço do $\textit{nó}$ criado é retornado.

## $\texttt{Verificar altura.}$

### $\texttt{Pseudocódigo.}$

```c
int altura(No *raizEsquerda, No *raizEsquerda)
	int a, b
	se (raizDireita == NULL) a = 0
		else a = raizDireita->altura
	se (raizEsquerda == NULL) b = 0
		else b = raizEsquerda->altura
	retorne ++(max(a, b))
```

### $\texttt{Código em C.}$

```c
int altura(No *raizDireita, No *raizEsquerda) {
    int a, b;
    if (raizDireita == NULL) a = 0;
        else a = raizDireita->altura;
    if (raizEsquerda == NULL) b = 0;
        else b = raizEsquerda->altura;
    return (a >= b) ? ++a : ++b;
}
```

$\textbf{Explicação.}$ 

## $\texttt{Inserir nó.}$

### $\texttt{Código em C.}$

```c
No* inserir(No* raiz, int valor) {
    if (raiz == NULL) {
        return criarNo(valor);
    }

    if (valor < raiz->valor) {
        raiz->esquerda = inserir(raiz->esquerda, valor);
    } else if (valor > raiz->valor) {
        raiz->direita = inserir(raiz->direita, valor);
    }

    raiz->altura = altura(raiz->esquerda, raiz->direita);

    return raiz;
}
```

### $\texttt{Função Void.}$

```c

```

### $\texttt{Inserção em árvore AVL.}$

```c
No *inserirNo(No *raiz, int chave) {
	if (raiz == NULL) {
		return criarNo(chave);
	}
	
	if (chave < raiz->chave) {
		raiz->esquerda = inserirNo(raiz->esquerda, chave);
	} else if (chave > raiz->chave) {
		raiz->direita = inserirNo(raiz->direita, chave);
	}
	
	raiz->altura = altura(raiz->esquerda->altura, raiz->direita->altura);
	switch(raiz->esquerda->altura - raiz->direita->altura) {
		case 2: rotacaoDireita(); break;
		case -2: rotacaoEsquerda(); break;
		default: break;
	}
	return raiz;
}
```

$\textbf{Explicação.}$ Atua em conjunto com a função `criarNo()` para inserir a estrutura recém-criada na posição correta na árvore binária. Assim sendo, percorremos cada nó e verificamos se a chave do nó criado é menor ou maior em relação à chave do nó atual. Com efeito, deslocamos nossa posição para a esquerda ou direita dependendo e, quando atingimos o `NULL`, fazemos a função `criarNo()` retornar o nó ao endereço correto da árvore. 

## $\texttt{Busca nó.}$

### $\texttt{Pseudocódigo.}$

```c
busca(raiz, x)
	pai = NULL
	ponteiro = raiz
	enquanto (ponteiro != NULL) e (ponteiro->chave != x)
		pai = ponteiro
		se x < ponteiro->chave
			ponteiro = ponteiro->esquerda
		senão
			ponteiro = ponteiro->direita
	retorne pai, ponteiro
```

### $\texttt{Código em C.}$

O algoritmo de busca descrito abaixo se refere ao implementado por mim e, portanto, não retorna dois ponteiros como o demonstrado no pseudocódigo.

```c
No *buscaNo(No *raiz, int chave) {
	if (raiz == NULL || raiz->chave == chave) {
		return raiz;
	}
	
	if (chave < raiz->chave) {
		return buscaNo(raiz->esquerda, chave);
	} else return buscaNo(raiz->direita, chave);
}
```

**Complexidade.** Possui complexidade $\mathcal{O}(n\log n)$ 

## $\texttt{Remover chave.}$

### $\texttt{Pseudocódigo.}$

```c
remover(raiz, x)
	pai, ponteiro = busca(raiz, x)
	se ponteiro == NULL
		Imprime("Não existe")
	senão
		se pai == NULL
			paiSucessor, suc = sucessor(pai)
			se suc == NULL
				old = raiz
				raiz = raiz->esquerda
				libere(old)
			senão
				raiz->chave = sucessor->chave
				se paiSucessor == raiz
					raiz->direita = sucessor->direita
				senão
					paiSucessor->esquerda = sucessorDireita
		senão
			paiSucessor, sucessor = sucessor(ponteiro)
			se sucessor == NULL
				se pai->chave > x
					pai->esquerda = ponteiro->esquerda
				senão
					pai->direita = ponteiro->direita
					libere(ponteiro)
			senão
				ponteiro->chave = sucessor->chave
				se paiSucessor = ponteiro
					ponteiro->direita = sucessor->direita
				senão
					paiSucessor->esquerda = sucessor->direita
				libere(sucessor)
```

## $\texttt{Impressão.}$

Considere a seguinte árvore binária de busca,
```tikz
\begin{document}
\begin{tikzpicture}[every node/.style={circle, draw, minimum size=1cm}]
  \node (50) {50}
    child {node (20) {20}
      child {node (10) {10}} % Adicione o nó 10 como filho de 20
      child {node (40) {40}}
    }
    child {node (70) {70}};
\end{tikzpicture}
\end{document}
```

Iremos analisar os algoritmos de impressão em cada caso separadamente e implementar a árvore binária dada acima como exemplo dessa impressão.

### $\texttt{Em ordem.}$

```c
void emOrdem(No *raiz) {
	if (raiz != NULL) {
		emOrdem(raiz->esquerda);
		printf("%d ", raiz->chave);
		emOrdem(raiz->direita);,
	}
}
```

O algoritmo de impressão em ordem percorre a árvore binária a partir das subárvores esquerda e ramifica para os nós direitos das subárvores esquerdas caso existirem. Posto isso, retornamos à raiz, imprimimos seu conteúdo `50` e , por fim, nos direcionamos à subárvore direita sempre dando prioridade aos nós esquerdos.

Para o exemplo dado, teremos a seguinte saída

```
20 40 50 70
```

### $\texttt{Pré-ordem.}$

```c
void preOrdem(No* raiz) {
    if (raiz != NULL) {
        printf("%d ", raiz->chave);
        preOrdem(raiz->esquerda);
        preOrdem(raiz->direita);
    }
}
```

O algoritmo de pré-ordem realiza a travessia em uma árvore binária começando pelo nó raiz e partindo para todas as subárvores esquerdas e, por fim, para as direitas. Desse modo, para caminharmos sobre a árvore binária em pré-ordem, empregamos recursão para chamar os nós situados à esquerda e depois à direita.

Para o exemplo dado, teremos a saída

```
50 20 40 70
```

### $\texttt{Pós-ordem.}$

```c
void posOrdem(No* raiz) {
    if (raiz != NULL) {
        posOrdem(raiz->esquerda);
        posOrdem(raiz->direita);
        printf("%d ", raiz->chave);
    }
}
```

Por outro lado, o algoritmo de pós-ordem percorre a árvore binária começando pelas subárvores esquerdas, depois parte para as direitas e, posteriormente, para a raiz. Posto isso, simplesmente invertemos a ordem da impressão no algoritmo. Por exemplo, considere a seguinte árvore binária

Para o exemplo sugerido, teremos

```
40 20 70 50
```

### $\texttt{Em nível.}$

#### $\texttt{Pseudocódigo.}$

Aqui está o pseudocódigo do professor.

```c
emNivel(raiz)
	se raiz != NULL
		insereFila(raiz)
	enquanto (fila não vazia)
		ponteiro = tiraFila()
		Imprime(ponteiro->chave)
		insereFila(ponteiro->esquerda)
		insereFila(ponteiro->direita)
```

$\textbf{Explicação.}$ Como podemos notar, a impressão por nível não é recursiva, ou seja, a própria função não é chamada dentro de si. Posto isso, inserimos o nó da raiz na fila por meio do `insereFila` inicialmente caso não for nula e entramos na condição de repetição enquanto a fila não estiver vazia. Por conseguinte, chamamos a função `tiraFila` que nos retornará o conteúdo do nó removido o qual será impresso. Por fim, inserimos as ramificações esquerdas e direitas com 

Aqui está o pseudocódigo proposto pelo Milton.

```c
vazio emNivel(No *raiz, No **inicio, No **fim)
	se raiz == NULL
		insere(inicio, fim, raiz)
	
	enquanto(inicio != NULL e fim != NULL)
		No *ponteiro = remove(inicio, fim)
		imprima(pt->chave)
		insere(inicio, fim, ponteiro->esquerda)
		insere(inicio , fim, ponteiro->direita)
```
