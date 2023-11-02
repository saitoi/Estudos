---
aliases:
  - abstract
tags:
  - java/classes
date: 2023-11-01
time: 19:15
complete:
---

# Classes Abstratas

> $\textit{Definição.}$ Refere-se a uma classe que não pode ser instanciada, uma vez que serve de *molde* para a criação de novas [[Subclasses|subclasses]] derivadas desta.

- [i] Classes abstratas não podem ser privadas, pois necessitam de subclasses concretas para a implementação da classe original.

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

Não é possível declarar instâncias/objetos de uma classe abstrata, apenas das **subclasses concretas** derivadas de uma abstrata. Por exemplo, a criação do objeto `Animal baleia = new Animal()` não é permitida.

Vale ressaltar que uma classe abstrata pode ter subclasses abstratas também, no entanto é necessário uma subclasse final concreta para a implementação do código.

## $\texttt{Métodos Abstratos.}$

Refere-se a um método que não possui implementação, sendo definido exclusivamente em uma classe abstrata. Indica que todas as subclasses derivadas possuem **um comportamento em comum** com sua implementação detalhada nas classes concretas.

Aqui está um exemplo de métodos abstratos.

```java
public abstract class Animal {
	public abstract void move();
	public abstract void makeNoise();
}
```

Os métodos `move()` e `makeNoise()` são abstratos e, portanto, não possuem implementação direta, apenas nas subclasses concretas.

- [i] Métodos abstratos **não podem ser abstratos**, pois as subclasses necessitam ter acesso ao método para a implementação.

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




