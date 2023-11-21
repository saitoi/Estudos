---
aliases:
  - patricia
tags:
  - ED
date: 2023-10-31
time: 13:47
complete:
---
# Árvore Patrícia

> $\textit{Definição.}$ Estrutura de dados do tipo árvore ordenada que se trata de uma representação compacta da [[Árvore Digital (Trie)|árvore trie]] em que os nós que possuem apenas um filho seriam agrupados com seus antecessores.

> [!info] Patrícia $\times$ Trie
> Nas árvores digitais, a string não é representada explicitamente nos nós de modo que devemos formá-la à medida que avançamos nas arestas das árvores. Por outro lado, nas árvores patrícias as strings resultantes são representadas por completo nos nós e, portanto, facilitam uma representação mais compacta.

## $\texttt{Inserção.}$

A inserção em uma árvore patrícia corresponde a procurar uma dada string até o ponto em que a busca se encerra, isto é, a string não foi encontrada. Com efeito, devemos inserir um nó na **última aresta percorrida** que armazena a posição onde as chaves diferem, além de ter como filhos o nó original que estava na extremidade da borda e um novo nó com a parte restante da nova chave.

Suponha que desejamos inserir a string "cadeira" em uma árvore patrícia existente:

![[Inserção Patrícia.svg|center|800]]

