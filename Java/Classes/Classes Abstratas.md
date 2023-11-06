---
aliases:
  - abstract
  - instanceof
tags:
  - java/classes
date: 2023-11-01
time: 19:15
complete:
---

# Classes Abstratas

> $\textit{Definição.}$ Refere-se a uma classe que não pode ser instanciada, uma vez que serve de *molde* para a criação de novas [[Subclasses|subclasses]] derivadas desta.

## $\texttt{Declaração.}$

Para declarar uma classe abstrata, empregamos o modificador `abstract` no nome da classe. Considere o exemplo abaixo da classe abstrata `Animal`.

```java
public abstract class Animal {
	protected String species;
	protected int age;
	
	public void eat() {
		System.out.println("O animal " + this.species + " comeu.");
	}	
}
```

Não é possível chamar o construtor de uma classe abstrata apenas das **subclasses concretas** derivadas de uma abstrata. Por exemplo, a criação do objeto `Animal baleia = new Animal()` não é permitida. No entanto, podemos usar a **palavra-chave** `Animal` para se referir a objetos criados de uma subclasse concreta.

Vale ressaltar que uma classe abstrata pode ter subclasses abstratas também, no entanto é necessário uma subclasse final concreta para a implementação do código.

- [i] Classes abstratas não podem ser privadas, pois necessitam de subclasses concretas para a implementação da classe original e, portanto, devem ser acessíveis.

> [!info] Visibilidade
> Métodos abstratos **não podem ser privados**, pois as subclasses necessitam ter acesso ao método para a implementação.

## $\texttt{Métodos Abstratos.}$

Refere-se a um método que não possui implementação, sendo definido exclusivamente em uma classe abstrata. Indica que todas as subclasses derivadas possuem **um comportamento em comum** de modo que sua implementação **precisa** ser detalhada nas subclasses concretas.

Aqui está um exemplo de métodos abstratos.

```java
public abstract class Animal {
	public abstract void move();
	public abstract void makeNoise();
}

public class Tartaruga extends Animal {
	@Override
	public void move() {
		/* ... */
	}
	@Override
	public void makeNoise() {
		/* ... */
	}
}
```

Os métodos `move()` e `makeNoise()` são abstratos e, portanto, devemos usar a anotação `@Override` e implementar o método nas classes concretas.

## $\texttt{Subclasses Abstratas.}$

Diferentemente de subclasses concretas, as subclasses abstratas (que derivam de uma superclasse também abstrata) possuem mais flexibilidade, ou seja,

- É possível implementar todos os métodos da classe abstrata pai.
- É possível implementar alguns desses métodos.
- É possível não implementar nenhum.
- É possível incluir métodos adicionais abstratos que devem ser implementados por alguma classe concreta.

## $\texttt{Polimorfismo.}$

As subclasses de uma classe abstrata podem ser tratadas da mesma forma, seguindo os mesmos padrões e regras definidas para a classe abstrata. Isso que o mesmo código possa manipular objetos de diferentes subclasses.

Aqui está um exemplo de polimorfismo aplicado às subclasses de classe abstrata:

```java
public abstract class Person {
	/* ... */	
}

public abstract class Worker extends Person {
	/* ... */
}

public abstract class Boss extends Person {
	/* ... */
}

public static void main(String[] args) {
	ArrayList<Person> people = new ArrayList<>();
	people.add(new Worker(/* ... */));
	people.add(new Boss(/* ... */));
	
	public static void raiseSalary(Person person) {
		/* ... */	
	}
}
```

Como podemos perceber, temos duas subclasses de `Worker` e `Boss` derivadas de `Person`, as quais podem ser tratadas da mesma forma ao empregar **listas**, **métodos** e outras estruturas envolvendo a superclasse `Person`.

Podemos obter as informações das subclasses concretas derivadas de uma abstrata. Para demonstrar isso, continuaremos o exemplo anterior.

```java
public abstract class Animal {
	/* ... */
	public String getExplicitType() {
		return getClass().getSimpleName() + " (" + this.species + ")";
	}
}
```

Podemos ver que o método `getExplicitType()` retorna o nome da classe associado ao nome da `species`. 

## $\texttt{Comando }$`instanceof`

A palavra-chave `instanceof` serve para identificar objetos que são instâncias de uma determinada subclasse. Considere que criamos um `ArrayList<Person>` e precisamos identificar quais objetos pertencem à classe `Boss`.

```java
public static void main(String[] args) {
	ArrayList<Person> people = new ArrayList<>();
	people.add(new Worker(/* ... */));
	people.add(new Boss(/* ... */));
	
	for (Person specificPerson : people) {
		if (specificPerson instanceof Boss boss) {
			boss.method1(/* ... */);
		}
	}
}
```

No exemplo acima, percorremos o `ArrayList` `people` e verificamos se encontramos algum objeto que é instância da classe `Boss` e, caso for, chamamos algum método relacionado a ele.




