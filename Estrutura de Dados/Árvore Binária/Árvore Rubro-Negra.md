---
aliases:
  - rubro
  - negra
tags:
  - ED/árvores
date: 2023-10-05
time: 14:02
complete:
---
# Árvore Rubro-Negra

> $\textit{Definição.}$ Árvore binária de busca cujas propriedades específicas estão listadas abaixo.

Por definição, satisfazem as seguintes propriedades:

1. Todo nó externo (nulo) é Negro.
2. Se $v$ é pai de $u$ e $u$ é Rubro, então $v$ é Negro.
3. Todo caminho (simples) da raiz até o nó externo tem o mesmo número de nós negros.

Expressão: $n>2^{\textup{NN}}-1$

## $\texttt{Inserção.}$

### $\texttt{Pseudocódigo.}$

```c
inserção
	insereArvoreBinaria
	pinta novo de R
	se pai de novo é R
		conserta
```

## $\texttt{Consertar.}$

### $\texttt{Pseudocódigo.}$

```c
conserta(No *nó)
	se (nó é R e pai é R)
		se pai é Raiz
			colore pai de N
		se tio é R
			recolore pai, tio, avo
			conserte(avo)
		senão
			rotação
```

## $\texttt{Left-Leaning Tree.}$

> $\textit{Definição.}$ Variação da árvore rubro-negra em que cada nó tem no máximo um filho à esquerda vermelho.

## $\texttt{Inserção.}$

### $\texttt{pseudocódigo.}$

```c
insereLL(raiz, x)
	se raiz = NULL
		raiz = aloca(..)
		raiz->chave = x
		raiz->esquerda = raiz->direita = NULL
		raiz->cor = R
		ret;
	se (cor(raiz->esquerda) = R) e (cor(raiz->direita) = R)
		recolore(raiz)
	se x < raiz->chave
		insere(raiz->esquerda, x)
	senão
		insere(raiz->direita, x)
	se (cor(raiz->esquerda) = N) e (cor(raiz->direita) = R)
		rotaçãoEsquerda(raiz)
	se (cor(raiz->esquerda) = R) e (cor(raiz->esquerda->esquerda) = N)
		rotaçãoDireita(raiz)

insereRNLL(raiz, x)
	insereLL(raiz, x)
	raiz->cor = N
```

