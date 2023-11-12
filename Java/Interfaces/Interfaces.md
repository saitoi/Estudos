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

## $\texttt{Declaração.}$

A declaração de uma interface é realizada por meio da **palavra-chave `interface`** no nome da classe. Considere o exemplo abaixo.

```java
public interface FlightEnabled { /* ... */ }

public interface Trackable { /* ... */ }
```

Como podemos ver, temos duas interfaces `FlightEnabled` e `Trackable` as quais podem conter métodos que deverão ser implementados pelas subclasses que implementarem essas interfaces.

> [!info] Visibilidade
> Ao omitir os modificadores de acesso em um membro de uma interface, o objeto declarado será implicitamente público.

## $\texttt{Comando implements.}$

Para associarmos uma classe a uma interface, empregamos a **palavra-chave `implements`** semelhante a `extends` para subclasses.

- [i] Uma classe pode estender apenas uma superclasse (herança única), no entanto uma classe pode implementar mais de uma interfaces. Podemos também estender e implementar simultaneamente.

Aqui está um exemplo de uma subclasse que implementa as duas interfaces mencionadas anteriormente.

```java
public class Bird implements FlightEnabled, Trackable { /* ... */ }
```

Por outro lado, podemos também estender e implementar a classe `Bird` simultaneamente, tal como abaixo:

```java
public class Bird extends Animal implements FlightEnabled, Trackable { 
	/* ... */ 
}
```

### <span style="color:#ff0000">Reformular seção abaixo.</span>

## $\texttt{Referência e Tipos Abrangentes.}$

Tendo em vista o exemplo da seção anterior, podemos criar um objeto da classe `Bird` e fazer referência a ele de formas distintas tal como abaixo:

```java
Animal abstractBird = new Bird(/* ... */);
FlightEnabled flightBird = new Bird(/* ... */);
Trackable trackedBird = new Bird(/* ... */);
```

Ao utilizar essas interfaces e classes para fazer referência a objetos da classe `Bird`, podemos apenas empregar os métodos referentes às interfaces ou classes abstratas específicos.

```java
abstractBird.someAnimalMethod( /* ... */ );
flightBird.someFlightEnabledMethod( /* ... */ );
trackedBird.someTrackableMethod( /* ... */ );
```

## $\texttt{Métodos da Interface.}$

Todos os métodos declarados em uma interface são **públicos e abstratos** por definição e, assim, deverão ser implementados e também conter apenas a assinatura sem nenhum código. Aqui está um exemplo:

```java
public interface FlightEnabled {
	void takeoff();
	void fly();
}
```

Assim como na implementação dos métodos abstratos de classes abstratas, devemos usar a anotação `@Override` ao implementar os métodos de uma interface.

## $\texttt{Campos da Interface.}$

Todos os campos de uma interface são implicitamente **públicos, finais e estáticos**. Isso implica que não podem ser modificados e devem ser obtidos por meio de uma referência à interface em questão e não ao objeto. Aqui está um exemplo:

```java
public interface Limites {
	int VALOR_MINIMO = 0;
	/* ... */
}
```

O atributo `VALOR_MINIMO` pode ser obtido de uma subclasse ao fazermos `Limites.VALOR_MINIMO` e por aí em diante.

## $\texttt{Interfaces Estendem Interfaces.}$

Assim como classes, interfaces podem ser estendidas por meio da **palavra-chave `extends`** de outras interfaces. A **palavra-chave `implements`** não deve ser utilizada. Aqui vai um exemplo:

```java
interface OrbitEarth extends FlightEnabled {
	/* ... */
}
```
