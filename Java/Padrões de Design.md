---
aliases:
  - padroes_design
  - pattern
tags:
  - java
date: 2023-11-06
time: 13:51
complete:
---

# Padrões de Design

> $\textit{Definição.}$ Refere-se a soluções reutilizáveis  para problemas comuns de design de software.

Os principais tipos de padrões de projeto podem ser categorizados nos seguintes grupos:

1. **Padrões de Criação**:  
	1. **Singleton**: Garante a existência de apenas uma instância de uma classe e fornece um ponto global de acesso a essa instância.
	2. **Factory**: Permite a criação de objetos sem especificar a classe exata do objeto que será criado. Isso é realizado por uma interface ou classe base comum que declara um método para criar objetos. Feito isso, são declaradas classes bases que implementam esse método para objetos específicos. As duas principais categorias do padrão "Factory" são:
		1. **Factory Method**: Define uma interface para criar objetos, permitindo que as subclasses escolham as classes concretas que serão instanciadas.
		2. **Abstract Factory**: Fornece uma interface para criar famílias de objetos sem especificar as classes concretas. Útil para a criação de objetos pertencentes a um conjunto de classes relacionadas.
2. 

## $\texttt{Factory.}$



### $\texttt{Vantagens de Factory.}$

1. A criação de objetos está concentrada em somente um lugar e qualquer classe que precise criar um objeto específico utiliza a classe `Factory`.
2. As classes que precisam de objetos específicos não precisam conhecer todos os objetos que podem ser criados.
3. O código é dinâmico, podemos mudar de uma implementação de `Factory` para outra.

