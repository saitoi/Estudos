---
aliases:
  - graduada
tags:
  - ED/Árvores
date: 2023-10-10
time: 14:10
complete:
---
# Árvore Graduada

> $\textit{Definição.}$ Estrutura de dados de árvore binária de busca hierárquica em que todos os nós da árvore possuem um rótulo/posto (número inteiro).

Por definição, as árvores graduadas obedecem as seguintes condições:

1. Posto de externo é $\cancel{0}$.
2. Posto de pai de externo é 1.
3. Se $v$ é pai de $u$, então $\text{posto}(v)$ é igual ao $\textup{posto}(u)$ ou ao $\text{posto}(u)+1$
4. Se $v$ é avô de $u$, então $\textup{posto}(v)$ é maior que $\textup{posto}(u)$.

Se analisarmos bem, a árvore graduada é nada mais que uma [[Estrutura de Dados/Árvore Binária/Árvore Rubro-Negra|árvore rubro-negra]] porém empregando a lógica do posto para identificar os nós da árvore ao oposto de utilizar a coloração.

Aqui está um exemplo de uma árvore graduada semelhante à árvore rubro-negra.

![[Árvore Graduada.svg|550]]
- [i] Como podemos ver, os nós cujos filhos possuem o mesmo posto correspondem aos nós rubros e negros da árvore rubro-negra.

**Obs.**  Esse conteúdo não é cobrado em provas, uma vez que esse tipo de estrutura equivale às árvores rubro-negras.



![[Vídeo Aula ED - Remoção em RN.mp4]]
