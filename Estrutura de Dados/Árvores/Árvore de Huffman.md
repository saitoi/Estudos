---
aliases:
  - huffman_tree
tags:
  - ED/Árvores
date: 2023-11-19
time: 11:28
complete:
---
# Árvore de Huffman

> $\textit{Definição.}$ Estrutura de dados usada para compressão de dados, onde caracteres mais frequentes têm códigos binários menores, otimizando a representação de dados na forma de uma árvore binária.

## $\texttt{Inserção.}$

O processo de inserção em uma árvore de Huffman é usualmente aplicado quando se deseja codificar uma sequência de caracteres de forma otimizada e representar cada um em uma estrutura de árvore binária. Como foi dito anteriormente, ordenamos os caracteres segundo suas frequências e feito isso formamos pares de "dois em dois" com a soma das frequências dos pares da seguinte forma:

