---
alias: null
tags: java
date: 2023-08-31
time: 15:52
---

# Substrings

Os métodos responsáveis pelo recorte de uma substring de uma string estão descritos abaixo:

1. `.substring(int beginIndex)`: Retorna a substring que inicia a partir do índice especificado. No exemplo abaixo estamos selecionando a segunda parte da frase `"World!"`:

```java
String greeting = "Hello, World!";
System.out.println("Hi " + greeting.substring(7)); /* "Hi World!" */
```

2. `.substring(int beginIndex, int endIndex)`: Retorna a substring contida no intervalo especificado. No exemplo abaixo estou selecionando a primeira parte do `"Hello"`:

```java
String greeting = "Hello, World!";
System.out.println(greeting.substring(0, 5) + " Pedro!"); /* Hello Pedro! */
```