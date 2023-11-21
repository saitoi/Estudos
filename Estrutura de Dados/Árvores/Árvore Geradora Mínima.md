---
aliases:
  - kruskal
  - conj_disjuntos
tags:
  - ED/Árvores
date: 2023-11-18
time: 18:27
complete:
---
# Árvore Geradora Mínima

> $\textit{Definição.}$ *Se trata da subárvore de um grafo ponderado que contém todos os vértices do grafo original e é gerada a partir da remoção de arestas, de modo a minimizar o peso total da árvore.*

Nesse sentido, dado um grafo ponderado qualquer, precisamos de um algoritmo que receba como entrada esse tipo de grafo e retorne sua árvore geradora mínima. Por esse motivo, normalmente, implementamos o **algoritmo de Kruskal**.
 
A complexidade total do algoritmo de Kruskal é $\mathcal{O}(m\log m)$.

## $\texttt{Conjuntos Disjuntos.}$

> $\textit{Definição.}$ *Estrutura de dados que mantém coleções de elementos disjuntos, agrupados em conjuntos distintos, onde cada conjunto não compartilha elementos com os outros conjuntos.*

Esse tipo de estrutura é comumente empregada em algoritmos de Union-Find, pois permite unir conjuntos e verificar a conexão de elementos de forma eficiente. Por esse motivo, utilizamos o conceito de conjuntos disjuntos na implementação do algoritmo de kruskal.

A implementação de conjuntos disjuntos costuma ser fácil de modo que existem apenas 2 funções essenciais para a implementação. As duas principais incluem:

1. `find()`: Responsável por encontrar um dado elemento, mais especificamente, o representante de seu conjunto. Ao implementar o `find()`, é comum utilizarmos a **compressão de caminhos** que será abordada posteriormente.
2. `une()`: Responsável por unir dois conjuntos quaisquer dado algum critério ou não de união. Usualmente, empregamos o **rank**/**altura** como critério, no entanto podemos também utilizar o **tamanho** (depende das especificações da questão).

De antemão, precisamos inicializar os conjuntos que desejamos alterar da seguinte forma:

```c
inicializar(Conj, n) {
	para (i de 1 até n) {
		conj[i] = i
	}
}
```

### $\texttt{Encontrar.}$

O processo de encontrar um elemento qualquer pertencente a um dos conjuntos envolve retornar 

```c
find(Conj, x) {
	enquanto (x != Conj[x]) {
		x = Conj[x]
	} 
	return Conj[x]
}
```

Procurar até encontrar o elemento representante do conjunto que aponta para si mesmo.

Find com compressão de caminhos:

```c
find(Conj, x) {
	y = x
	enquanto (Conj[y] != y) {
		y = Conj[y]
	} enquanto (Conj[x] != y) {
		pai = Conj[x]
		Conj[x] = y
		x = pai
	}
	return y
}
```

Complexidade: $\mathcal{O}(n)$.

### $\texttt{Unir.}$

```c
une(Conj, a, b) {
	a = find(a)
	b = find(b)
	se (a != b) {
		Conj[a] = b
	}
}
```

Complexidade: $\mathcal{O}(1)$.

Verificação:

```c
se (a != Conj[a] ou b != Conj[b]) {
		ERRO!
	}
```

União com critério de tamanho: Menor conjunto aponta para maior conjunto seguindo o critério de quantidade de elementos do conjunto.

```c
une(Conj, a, b) {
	se (tam[a] < tam[b]) {
		Conj[a] = b
		tam[b] += tam[a]
	} senão {
		Conj[b] = a
		tam[a] += tam[b]
	}
}
```
![[Continuação de Conjuntos Disjuntos e Union Find.mp4]]

União por critério de altura/rank:

```c
une(Conj, a, b) { 
	se alt[a] < alt[b] {
		conj[a] = b
	} senão {
		Conj[b] = a
		se (alt[a] == alt[b]) {
			alt[a]++
		}
	}
}
```

Compressão de caminhos: 