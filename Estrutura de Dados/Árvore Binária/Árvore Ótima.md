---
aliases:
  - otima
tags:
  - ED/Árvores
date: 2023-10-07
time: 16:50
complete:
---
# Árvore Ótima

> $\textit{Definição.}$ Árvore binária de busca cuja estrutura permite a realização de uma busca otimizada dos elementos.

- [i] Considere uma árvore binária de busca $T$ juntamente da frequência de acesso de cada nó dado pela figura abaixo.

![[Árvore Ótima.excalidraw.svg|650]]

A frequência de cada nó poderá ser calculada da seguinte forma <ins>se desconsiderarmos os nós nulos</ins>
$$
(1\cdot 100)+(2\cdot 10)+(3\cdot 5)+(4\cdot 1)=169
$$
Posto isso, ao considerarmos todos os nós de uma árvore binária de busca, definimos o custo de uma árvore ótima como sendo
$$
\textup{Custo}(T)=\sum_{i=1}^{n}f_{i}\cdot l_{i}^{T}+\sum_{i=1}^{n}f_{i}'\cdot (l_{i}'-1)
$$
De modo que,
- $f_{i}$ corresponde à frequência de acesso da chave $i$.
- $l_{i}$ equivale ao nível da chave $i$ em $T$.
- $f_{i}'$ corresponde à frequência dos nós nulos (entre outras chaves).
- $l_{i}'$ equivale ao nível dos nós nulos.

## $\texttt{Montando a Árvore Ótima.}$

A sequência de passos necessária para a montagem de uma árvore ótima dados $n$ nós será descrita abaixo.

1. Inicialmente, devemos ordenar de forma crescente todos os nós. Suponha que teremos a sequência $c_{1},c_{2},\dots,c_{n-1},c_{n}$ ao final da reorganização.
2. Considere que a indexação $(i,j)$ compreende o intervalo de $i$ até $j-1$.
3. Feito isso, devemos preencher três tabelas denotadas de $w,c$ e $R$ que se referem, respectivamente, aos seguintes dados:
	1. Tabela $w:$ Somatório das frequências das subárvores possíveis com os nós dados.
	2. Tabela $c:$ Custo real de todas as subárvores possíveis com o nó $k$.
	3. Tabela $R:$ Corresponde às raízes das subárvores com custo mínimo.
4. Para preenchermos as tabelas podemos utilizar algumas fórmulas gerais que serão descritas com detalhe nas seções abaixo:

### $\texttt{Tabela }$$w\texttt{:}$

Para determinarmos a frequência total de uma subárvore contendo os nós indexados de $i$ até $j-1$, utilizaremos a seguinte fórmula fechada:
$$
w(i,j)=\sum_{k-i}^{i-1}F_{k}+\sum_{k=i}^{j}F_{k}^{'}
$$
No entanto, a fórmula recursiva correspondente também é válida:
$$
w(i,j)=w(i,j-1)+F_{j-1}+F_{j}^{'}
$$
Ao começar a montar a tabela, notamos que a diagonal da árvore principal será preenchida com as frequências nulas $F'$ da árvore original.

Considerando o exemplo inicial teríamos:

|       | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- |
| **1** | 0   | 100 | 111 | 116 |
| **2** |     | 1   | 12  | 17  |
| **3** |     |     | 1   | 2   |
| **4** |     |     |     | 0   |

### $\texttt{Tabela}$ $c\texttt{:}$



### $\texttt{Tabela }$

6. Temos três tabelas, denotadas pelas letras $w,c$ e $R$
	1. Somatório $w(i,j)$ das frequências de todas as subárvores possíveis com os nós dados. A tabela pode ser resumida nas seguintes expressões:$$\begin{flalign}&\textup{Forma fechada: }w(i,j)=\sum_{k=i}F_{k}^{i-1}+\sum_{k=i}^{j}F_{k}^{'}&& \\&\textup{Forma recursiva: } w(i,j)=w(i,j-1)+F_{j-1}+F_{j}^{'}\end{flalign}$$Podemos perceber que a diagonal principal da tabela será sempre preenchidas com as frequências nulas $F'$ da árvore.
	2. Somatório $c(i,j)$ do custo real de todas as subárvores possíveis com os nós dados. A tabela pode ser encontrada com o seguinte cálculo. $$c_{i,j}=w(i,j)+\textup{min}_{k=i}^{j-1}(c(i,k)+c(k+1,j)).$$Por consequência, a diagonal principal da tabela $c(i,j)$ é a mesma que $w(i,j)$, pois o o termo $\textup{min}_{k=i}^{j-1}$ é sempre nulo quando $i=j$ e, assim, teremos apenas o fator $w(i,j)$.
	3. Por fim, nos resta completar a tabela $R$ correspondente às chaves com custo mínimo dentre todas as subárvores $(i,j)$ possíveis de serem formadas.$$R=K_{min}.$$De modo que $K$ representa o índice empregado na expressão do custo mínimo.
