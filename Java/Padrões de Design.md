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

1. **Padrões de Criação**: Aborda a questão da geração de instâncias de objetos e classes, bem como as dependências entre si.
	1. **Singleton**: Garante a existência de apenas uma instância de uma classe e fornece um ponto global de acesso a essa instância.
		1. **Eager Singleton**: Instância única é criada no momento em que a classe é carregada na memória, isto é, uma criação antecipada. Pode consumir mais recursos.
		2. **Lazy Singleton**: Instância única é criada apenas quando houver necessidade, ou seja, de forma preguiçosa. Isso economiza recursos, porém pode gerar sobrecarga na hora de criação da instância.
	3. **Factory**: Permite a criação de objetos sem especificar a classe exata do objeto que será criado. Isso é realizado por uma interface ou classe base comum que declara um método para criar objetos. Feito isso, são declaradas classes bases que implementam esse método para objetos específicos. As duas principais categorias do padrão "Factory" são:
		1. **Factory Method**: Define uma interface para criar objetos, permitindo que as subclasses escolham as classes concretas que serão instanciadas.
		2. **Abstract Factory**: Fornece uma interface para criar famílias de objetos sem especificar as classes concretas. Útil para a criação de objetos pertencentes a um conjunto de classes relacionadas.
2. **Padrões de Comportamento**: Tratam do comportamento e interação entre objetos e classes. Concentram-se na colaboração de objetos para cumprir responsabilidades e na atribuição das mesmas aos objetos.
	1. **Observer**: Define uma dependência de um-para-muitos entre objetos de modo que quando um objeto muda de estado, todos os seus dependentes são notificados e atualizados.
3. **Padrões de Estrutura**: Concentram-se na organização de classes e objetos para compor estruturas maiores e mais complexas.

## $\texttt{Singleton.}$

Como vimos anteriormente, o padrão de design "Singleton" se refere à criação e tratamento de uma única instância de uma classe particular no programa.

Aqui está o código base para a criação de uma classe `Singleton` e sua implementação.

```java
public class Singleton {
	private Singleton uniqueInstance;
	
	private Singleton() {
	
	}
	
	public static synchronized Singleton getInstance() {
		if (uniqueInstance == null) {
			return new Singleton();
		} else return uniqueInstance;
	}
}

public class Principal {
	public static void main(String[] args) {
		Singleton singleton = Singleton.getInstance();
		
		System.out.println(singleton);
		System.out.println(Singleton.getInstance());
	}
	/* ... */
}
```

Como podemos ver, declaramos uma instância privada e estática de `Singleton` dentro da própria classe juntamente de um **construtor privado**. Feito isso, restringimos a utilização desse construtor ao método estático `getInstance` Isso impede a criação de instâncias fora da classe, apenas em seu interior.

- [i] A palavra-chave `synchronized` restringe utilização do método por mais de uma **thread** simultaneamente, ou seja, está "sincronizado".

Denominamos essa aplicação de **Lazy Singleton**, ou seja, apenas declaramos uma instância de `Singleton` quando for necessário, mais especificamente no interior do método `getInstance` da classe.

No entanto, podemos também declarar uma única instância de `Singleton` no início do programa e não alterá-la da seguinte forma:

```java
public class Singleton {
	public static final Singleton = new Singleton();
	private Singleton() {
	
	}
	/* ... */
}
```

Chamamos essa implementação de **Eager Singleton**, ou seja, uma única instância é criada e carregada na memória de forma antecipada.

## $\texttt{Factory.}$



### $\texttt{Vantagens de Factory.}$

1. A criação de objetos está concentrada em somente um lugar e qualquer classe que precise criar um objeto específico utiliza a classe `Factory`.
2. As classes que precisam de objetos específicos não precisam conhecer todos os objetos que podem ser criados.
3. O código é dinâmico, podemos mudar de uma implementação de `Factory` para outra.

## $\texttt{Observer.}$




