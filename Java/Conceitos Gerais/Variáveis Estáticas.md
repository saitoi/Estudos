---
aliases:
  - estatica_variaveis
  - static_variables
tags:
  - java
date: 2023-10-18
time: 11:18
complete: false
---

# Variáveis Estáticas

> $\textit{Definição.}$ Variável que pertence à classe ao invés de pertencer a instâncias individuais dessa classe e, portanto, se trata de uma variável compartilhada por todas as instâncias de uma classe.

Declaramos uma variável estática por meio da palavra-chave `static`. Aqui está um exemplo da utilização de uma variável estática `contador`.

```java
public class Exemplo {
	static int contador;
	
	public Exemplo() {
		++contador;
	}
	
	public static void main(String[] args) {
		Exemplo exemplo1 = new Exemplo();
		Exemplo exemplo2 = new Exemplo();
		
		System.out.println("Contador: %d", Exemplo.contador); /* "Contador: 2" */
		System.out.println("Contador: %d", exemplo1.contador); /* "Contador: 2" */
		System.out.println("Contador: %d", exemplo2.contador); /* "Contador: 2" */
	}
}
```



