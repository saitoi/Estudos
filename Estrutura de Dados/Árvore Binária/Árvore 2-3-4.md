---
aliases:
  - "234"
tags:
  - ED/Árvores
date: 2023-10-15
time: 23:50
complete:
---
# Árvore 2-3-4

> $\textit{Definição.}$ Árvore binária de busca cujas propriedades específicas estão listadas abaixo.

Por definição, as árvores 2-3-4 seguem os seguintes princípios:

1. Cada nó tem 2, 3 ou 4 filhos.
2. Todas as folhas estão situadas no mesmo nível.
3. Se o nó possui $k$ chaves, então ele possui $k+1$ filhos.
4. Apenas as folhas possuem filho nulo.

Podemos ordenar os filhos de uma árvore 2-3-4 de tal forma que

![[Árvore 2-3-4.svg|450]]

- [i] O lado exato dos nós com chaves iguais não importa para a organização da árvore.

## $\texttt{Inserção.}$

Inicialmente, inserimos todas as chaves em uma mesma folha até termos 3 chaves. Feito isso, antes de inserir a quarta chave, quebraremos o nó atual em três partes e, então, a inserção será realizada. Aqui está um exemplo.

![[Inserção Árvore 2-3-4.svg]]

Embora não pareça, a árvore 2-3-4 não é nada mais que uma [[Estrutura de Dados/Árvore Binária/Árvore Rubro-Negra|árvore rubro-negra]] porém organizada de forma diferente. Podemos pensar da seguinte forma:
![[Conversão 2-3-4 e Árvore RN.svg]]
Por esse motivo, eventualmente, teremos uma árvore rubro-negra ao realizar todas essas modificações à árvore **2-3-4**.

## $\texttt{Remoção.}$