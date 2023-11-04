---
aliases:
  - arraylist
tags:
  - java
date: 2023-10-17
time: 10:14
complete:
---

# ArrayList

> $\textit{Definição.}$ Classe em Java que permite a implementação de listas dinâmicas de objetos, ou seja, redimensionáveis na execução do programa.

- [i] De antemão, para usarmos as `ArrayList`, precisamos importar o pacote `java.util.ArrayList`.

## $\texttt{Declaração.}$

Suponha a criação de uma lista dinâmica de objetos do tipo `String`, então faremos assim abaixo.

```java
ArrayList<String> listaDeStrings = new ArrayList<>();
```

## $\texttt{Métodos.}$

1. Adição de novos elementos: Empregamos o método `.add()` da classe `ArrayList` que adiciona o objeto à última posição da lista.

```java
listaDeStrings.add("Primeira palavra");
listaDeStrings.add("Segunda palavra");
listaDeStrings.add("Terceira palavra");

["Primeira palavra", "Segunda palavra", "Terceira palavra"]
```

2. Remoção de elementos: Empregamos o método `.remove()` para remover o último objeto da lista dinâmica.

```java
listaDeStrings.remove();
listaDeStrings.remove();

["Primeira palavra"]
```

3. Obter o tamanho da lista: O método `.size()` é útil para determinar o número de elementos da lista.

```java
System.out.println("O número de elementos da lista é " + listaDeStrings.size());
/* "O número de elementos da lista é 1" */
```

4. Conversão em uma array estático: Utilizamos o método `.toArray()` para converter a lista dinâmica em uma estática, retornando-a.

```java
String[] listaEstaticaStrings = new listaDeStrings.toArray();
```

5. Conter um elemento na lista dinâmica: Para verificarmos se a lista dinâmica contém algum elemento específico, podemos usar o método `.contains()`.

```java
boolean elementoContido = listaDeStrings.contains("Primeira palavra");
/* elementoContido ==> true */
```
