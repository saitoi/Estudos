---
aliases:
  - composicao
  - agregacao
tags:
  - java
date: 2023-11-12
time: 12:10
complete:
---

# Composição e Agregação

> $\textit{Definição.}$ Referem-se a conceitos relacionados à forma como as classes se associam umas às outras. Nesses tipos de relações entre classes, normalmente, uma das classes contém um ou mais instâncias da outra.

A relações de **agregação** e **composição** diferem entre si em função da força do vínculo entre as classes. Em uma agregação, embora uma classe contenha objetos da outra, essa "outra" pode existir independentemente, ou seja, a destruição do objeto todo não implica a destruição de seus componentes.

Por outro lado, na composição o vínculo entre as classes é mais forte e, portanto, a destruição do objeto completo implica a destruição de suas partes.

Aqui está um exemplo de uma **agregação**.

```java
public class Department {
	private String nome;
	private List<Employee> employees;
	/* ... */
}

public class Employee {
	private String nome;
	private int employeeId;
	/* ... */
}
```

Como podemos notar, a destruição do "objeto todo" não implica a destruição de seu componente `Employee`, por mais que um pertença ao outro.

Aqui vai um exemplo de uma **composição**.

```java
public class Engine {
	/* ... */
}

public class Car {
	private String model;
	private Engine engine;
	/* ... */
}
```

Entretanto, no caso acima, a eliminação da classe `Car` implica também a destruição de sua `Engine` pois uma depende da outra para sua existência.