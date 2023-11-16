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

![[Excalidraw/SVGs/Árvore Ótima.svg|650]]

**Desconsiderando os nós nulos,** podemos calcular a frequência de todos os nós da árvore considerando o nível de cada um da seguinte forma:
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
w(i,j)=\sum_{k=i}^{j-1}F_{k}+\sum_{k=i}^{j}F_{k}^{'}
$$
No entanto, a fórmula recursiva correspondente também é válida:
$$
w(i,j)=w(i,j-1)+F_{j-1}+F_{j}^{'}
$$
Ao começar a montar a tabela, notamos que a diagonal da árvore principal será preenchida com as frequências nulas $F'$ da árvore original.

Considerando o exemplo inicial teríamos:

|       | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| **0** |   0  |     |     |     |     |
| **1** | -    | 1   | 100 | 111 | 116 |
| **2** |  -   | -   | 1   | 12  | 17  |
| **3** |    - | -   | -   | 0   | 2   |
| **4** |   -  | -   | -   | -   |    |

### $\texttt{Tabela}$ $c\texttt{:}$

Tendo encontrado todas as frequências das subárvores indexadas de $(i,j)$, isto é, de $i$ até $j-1$. Calcularemos o custo mínimo possível dessas subárvores ao selecionarmos um dado $k$. Para isso, utilizaremos a seguinte fórmula:
$$
c(i,j)= w(i,j)+\textup{min}_{k=i}^{j-1}(c(i,k)+c(k+1,j))
$$
Interpretaremos essa expressão da seguinte forma:

-  $\textquotedblleft$O termo $c(i,j)$ da tabela $c$ corresponderá ao fator equivalente na tabela $w$ **juntamente** do mínimo da soma $c(i,k)+c(k+1,j)$ para algum $k$ compreendido no intervalo $[i,j-1]$$\textquotedblright$.

Com efeito, a diagonal da tabela $c$ será idêntica à da tabela $w$, pois o termo $\textup{min}_{k=i}^{j-1}$ teria que ir de $i$ até $i-1$ o que não é plausível de ser feito.

Tendo em vista o exemplo inicial, teremos a tabela:

|       | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- |
| **1** | 0   | 101 | 125 | 238 |
| **2** | -   | 1   | 14  | 125 |
| **3** | -   | -   | 1   | 21  |
| **4** | -   | -   | -   | 0   |

|       | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| **0** |   0  |     |     |     |     |
| **1** | -    | 1   | 100 | 111 | 116 |
| **2** |  -   | -   | 1   | 12  | 17  |
| **3** |    - | -   | -   | 0   | 2   |
| **4** |   -  | -   | -   | -   |    |

### $\texttt{Tabela}$ $R\texttt{:}$

Por fim, a tabela $R$ corresponde ao índice $k$ das chaves mínimas identificadas em cada uma das subárvores possíveis na tabela anterior. Desse modo, teremos a expressão
$$
R=K_{min}.
$$
Com base na tabela anterior, montaremos essa rapidamente.

|       | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- |
| **1** | -   | 1   | 1   | 2   |
| **2** | -   | -   | 2   | 2   |
| **3** | -   | -   | -   | 3   |
| **4** | -   | -   | -   | -   |

|       | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| **0** |   0  |     |     |     |     |
| **1** | -    | 1   | 100 | 111 | 116 |
| **2** |  -   | -   | 1   | 12  | 17  |
| **3** |    - | -   | -   | 0   | 2   |
| **4** |   -  | -   | -   | -   |    |