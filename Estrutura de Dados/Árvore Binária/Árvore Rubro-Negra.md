---
aliases:
  - rubro
  - negra
tags:
  - ED/Árvores
date: 2023-10-05
time: 14:02
complete:
---
# Árvore Rubro-Negra

> $\textit{Definição.}$ Estrutura de dados de árvore binária de busca que permite uma organização de dados de forma eficiente. São chamadas de $\textquotedblleft$rubro-negras$\textquotedblright$ em função da coloração dos nós (vermelho e preto).

Por definição, as árvores rubro-negras obedecem as seguintes condições:

1. Todo nó externo ou **nulo** é Negro.
2. Se $v$ é pai de $u$ e $u$ é Rubro, então $v$ é Negro.
3. Todo caminho (simples) da raiz até um nó externo tem o mesmo número de nós negros.

- [i] A raiz de uma árvore rubro-negra pode ser rubro desde que os filhos da raiz não sejam rubros. 

Segundo a terceira condição, o número de nós negros da raiz de uma árvore rubro-negra até um nó externo é sempre o mesmo, independentemente do caminho que escolhermos.

Aqui está um exemplo de uma árvore rubro-negra que atende todas as condições descritas:

![[Árvore Rubro-Negra.svg|550]]
- [i] Vale notar que não criamos uma árvore binária de busca para depois colorir os nós. Começamos com uma árvore rubro-negra e procuramos manter essa propriedade até o fim do algoritmo.

## $\texttt{Inserção.}$

A inserção em uma árvore rubro-negra começa inserindo em uma árvore binária de busca de modo que o nó inserido será sempre <span style="color:#ff0000">rubro</span>.

Feito isso, verificamos se o pai do nó inserido é <span style="color:#ff0000">rubro</span> e, caso positivo, chamaremos a função `conserta()` para consertar/colorir a árvore da forma correta.

Aqui está o pseudocódigo correspondente para essa função:

```c
inserção(No nó):
	insereArvoreBinária(árvore, nó)
	pinta novo nó de Rubro
	se (pai de novo nó é Rubro):
		consertar(nó)
```

## $\texttt{Consertar.}$

A função `consertar()` para a árvore rubro-negra é implementando quando há a necessidade de colorir alguns dos nós da árvore ou rotacioná-los dependendo do caso.

De antemão, a função será ativada apenas quando o <ins>nó inserido e seu pai forem <span style="color:#ff0000">rubros</span></ins>. Posto isso, verificamos as seguintes condições:

1. `Pai é Raiz`: Caso o pai for raiz da árvore rubro-negra, colorimos o pai de negro e não haverá mais nada a fazer. Isso corresponde à segunda inserção do nó na árvore rubro-negra ou quando estivermos voltando de uma recursão.
2. `Tio é Rubro`: Caso o tio do nó inserido for rubro, devemos colorir o pai e o tio de negros e o avô de <span style="color:#ff0000">rubro</span>. No entanto, caso o avô não for raiz da árvore, deveremos consertar os nós acima do avô e assim por diante.
3. `Tio não é Rubro`: Esse caso ocorrerá quando o tio for negro (nó externo provavelmente) e o pai for <span style="color:#ff0000">rubro</span>. Com efeito, teremos que rotacionar os nós a partir do nó inserido bem parecido com a rotação de uma árvore **AVL**.

O pseudocódigo para a função de consertar os nós da árvore será descrito abaixo. **Obs**. Não especificaremos o algoritmo da rotação no exemplo dado.

```c
consertar(No *nó):
	se (nó é Rubro e pai é Rubro)
		se pai é Raiz
			colore pai de Negro
		se tio é Rubro
			recolore pai, tio, avô
			conserte(avô)
		senão
			rotação()
```

## $\texttt{Remover.}$

## $\texttt{Vídeo: Provando Propriedades e Remoção em RN.}$

No vídeo aula abaixo, a seção de remoção em árvore rubro-negra se inicia no tempo 1:02:--

![[Remoção em RN.mp4]]

### $\texttt{Pseudocódigo.}$

```c

```

## $\texttt{Árvores Rubro-Negras Left-Leaning.}$

> $\textit{Definição.}$ Variação da estrutura de dados de árvore rubro-negra na qual os filhos rubros só poderem ser inseridos à esquerda, isto é, caso tenhamos apenas um filho rubro.

- [i] Nas árvores rubro-negras left-leaning, a raiz é sempre negra.

## $\texttt{Inserção.}$

De antemão, ao realizar uma inserção nesse tipo de estrutura de dados, realizamos o algoritmo de busca binária e, verificamos se passamos por algum nó negro com filhos <span style="color:#ff0000">rubros</span>, invertendo as cores entre o nó pai e seus filhos.

Feito isso, realizamos a inserção como em uma árvore binária de busca. Ao retornar da recursão, verificamos se algum nó à direita é <span style="color:#ff0000">rubro</span> e seu irmão é negro e realizamos uma **rotação esquerda** nessa ocasião.

Outrossim, também precisamos verificar se encontramos algum filho <span style="color:#ff0000">rubro</span> com um pai também <span style="color:#ff0000">rubro</span> e, caso tivermos, precisamos realizar uma **rotação direita**. Por fim, a raiz da árvore rubro-negra left-leaning é sempre negra de modo que colorimos ele no retorno da recursão.

Aqui está o pseudocódigo referente à inserção em uma árvore rubro-negra left-leaning.

```c
insereLL(raiz, x)
	se raiz = NULL
		raiz = aloca(..)
		raiz->chave = x
		raiz->esquerda = raiz->direita = NULL
		raiz->cor = R
		ret;
	se (cor(raiz) = N e (cor(raiz->esquerda)) = R) e (cor(raiz->direita) = R)
		recolore(raiz)
	se x < raiz->chave
		insere(raiz->esquerda, x)
	senão
		insere(raiz->direita, x)
	se (cor(raiz->esquerda) = N) e (cor(raiz->direita) = R)
		rotaçãoEsquerda(raiz)
	se (cor(raiz->esquerda) = R) e (cor(raiz->esquerda->esquerda) = R)
		rotaçãoDireita(raiz)

insereRNLL(raiz, x)
	insereLL(raiz, x)
	raiz->cor = N
```

Ao total podemos identificar três condições para as quais modificamos a cor dos nós ou necessitamos rotacioná-los, elas são:

![[Três Condições Árvore RN.svg|400]]
As setas para cima e para baixo indicam, respectivamente, que o programa está retornando ou avançando na recursão. Outrossim, os nós estão sendo coloridos corretamente à medida que identificamos um dos três casos acima.


## $\texttt{Vídeo: Árvores Rubro-Negras Left-Leaning.}$

![[Vídeo Aula ED - Árvore RN LL.mp4]]

![[Vídeo Aula ED Monitoria - Árvore RN.mp4]]