---
aliases:
  - generica
tags:
  - java/Classes
date: 2023-10-10
time: 10:11
complete:
---

# $\texttt{Genéricos.}$

> $\textit{Definição.}$ Recurso que permite criar classes, interfaces, métodos e outras estruturas de dados que são parametrizadas por tipos de dados. Isso permite a criação de códigos flexíveis o suficiente para trabalharmos com diferentes tipos de dados.

Podemos definir uma variedade de recursos como foi dito. Esses recursos (classes, métodos e variáveis) serão especificadas nas seções abaixo.

## $\texttt{Classes Genéricas.}$

> $\textit{Definição.}$ Também conhecidas como **classes parametrizadas**, trata-se de um recurso que permite criar classes que podem operar com tipos de dados diferentes, ou seja, uma classe ou método pode ser reutilizado com vários tipos.

### $\texttt{Declaração.}$

A declaração de uma classe genérica em Java envolve a utilização do operador `<>` englobando um tipo genérico, normalmente representado com a letra maiúscula `T`.

```java
public class MinhaClasse<T> {
	private T valor 
}
```

