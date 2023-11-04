---
alias: null
tags: java
date: 2023-08-31
time: 22:46
---

# Prefixo e Sufixo

Para realizar as verificações se a string inicia com uma dada sequência de caracteres (prefixo) ou termina com uma cadeia de caracteres (sufixo), empregamos os métodos abaixo:

1. `.startsWith(String prefix)`: Verifica se a string inicia com o prefixo `prefix` e retorna um booleano correspondente, tal como abaixo:

```java
String greeting = "Hello World!";
if (greeting.startsWith("Hello")) {
	System.out.println("This is a greeting.");  /* "This is a greeting" */
} else {
	System.out.println("This isn't greeting.");
}
```

2. `.endsWith(String suffix)`: Verifica se a string termina com o sufixo `suffix` e retorna um booleano correspondente. Aqui está um exemplo:

```java
String welcoming = "Hi Pedro";
if (welcoming.endsWith("Pedro")) {
	System.out.println("My name is Pedro.");  /* "My name is Pedro" */
} else {
	System.out.println("My name isn't Pedro.");
}
```