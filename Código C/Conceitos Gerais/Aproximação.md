---
aliases:
  - arredondamento
  - round_C
tags:
  - ⓒ/math
date: 2023-08-26
time: 18:41
complete: true
---

# Aproximação

> $\textit{Definição.}$ Refere-se às funções de arredondamento de valores em ponto flutuante importadas da [[Código C/Conceitos Gerais/Bibliotecas#^ec74da|biblioteca]] `math.h`.

## $\textrm{Principais funções.}$

|Função|Descrição|Exemplo de Uso|
|---|---|---|
|`ceil()`|Retorna o menor número inteiro maior ou igual ao valor em ponto flutuante fornecido.|`int teto = ceil(3.3)` // teto valerá 4|
|`floor()`|Retorna o maior número inteiro menor ou igual ao valor em ponto flutuante fornecido.|`int chao = floor(2.6)` // chao valerá 2|
|`round()`|Retorna o valor inteiro mais próximo, arredondado do ponto flutuante.|`int arredondado = round(3.5)` // arredondado valerá 4|
|`trunc()`|Retorna apenas a parte inteira do ponto flutuante.|`double truncado = trunc(3.14)` // truncado valerá 3.0|
|`rint()`|Retorna o valor arredondado para o inteiro mais próximo, usando o modo de arredondamento padrão da máquina.|`double arredondado_perto = rint(3.5)` // arredondado_perto valerá 4.0|