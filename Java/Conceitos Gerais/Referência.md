---
aliases:
  - reference
tags:
  - java
date: 2023-10-15
time: 18:46
complete:
---

# Referência

- [i] Podemos criar múltiplas referências para o mesmo objeto. Suponha a classe `House` com o atributo privado `cor` e método construtor não especificado abaixo, poderemos fazer

```java
public class Main {
	public static void main(String[] args) {
		House bluehouse = new House("blue");
		House sameHouse = blueHouse;
		
		blueHouse.setColor("red");
		System.out.println(blueHouse.getColor()); // Imprime "red"
		System.out.println(sameHouse.getColor()); // Imprime "red"
		
		House anotherHouse = new House("yellow");
		System.out.println(anotherHouse.getColor()); // Imprime "yellow"
		System.out.println(blueHouse.getColor()); // Imprime "red"
		System.out.println(sameHouse.getColor()); // Imprime "red"
	}
}
```

Como podemos notar, ao realizar a atribuição ``