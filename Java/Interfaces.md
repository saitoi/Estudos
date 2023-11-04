---
aliases:
  - inter
tags:
  - java
date: 2023-11-02
time: 13:36
complete:
---

# Interfaces

> $\textit{Definição.}$ Semelhante a uma [[Classes Abstratas|classe abstrata]], no entanto não se trata de uma classe. Corresponde a uma coleção de métodos abstratos/comportamentos que definem um "contrato" para as classes que a implementam. 

Para associarmos uma classe a uma interface, empregamos a palavra-chave `implements` semelhante a `extends` para subclasses.

- [i] Uma classe pode estender apenas uma superclasse (herança única), no entanto uma classe pode implementar mais de uma interfaces. Podemos também estender e implementar simultaneamente.

Aqui está um exemplo de duas interfaces juntamente de uma superclasse abstrata.

```java
public interface FlightEnabled { /* ... */ }

public interface Trackable { /* ... */ }

public abstract class Animal { /* ... */ }
```

Em outro arquivo, podemos criar uma subclasse `Bird` da seguinte forma:

```java
public class Bird extends Animal implements FlightEnabled, Trackable { 
	/* ... */ 
}
```

Tendo isso em vista, podemos fazer referência a um objeto da classe `Bird` 
