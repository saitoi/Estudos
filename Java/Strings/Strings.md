---
alias: strings_java strings_classe
tags: java/✖ java/Classes
date: 2023-08-09
time: 13:52
---

# Strings

> $\textit{Definição.}$ Classe especial em Java que permite a criação e manipulação de sequências de caracteres (<ins>strings</ins>). A classe pertence à [[Bibliotecas Python|biblioteca padrão do Java]] (`java.lang`), mais especificamente `java.lang.String`.

## Declaração

Podemos declarar variáveis do tipo `String` de duas formas:

1. **Comando `new`**
	- Ao empregar essa palavra-chave, estamos criando um novo objeto do tipo `String` explicitamente, embora o conteúdo da string já exista. Aqui está um exemplo abaixo:
	```java
	String str1 = new String("Hello");
	String str2 = new String("Hello");
	```
	- Pode resultar em desperdício de memória, pois objetos distintos se referem ao mesmo conteúdo e <ins>em Java strings são imutáveis</ins>.

2. **Diretamente**
	- Declaração da variável do tipo `String` sem necessidade de palavras-chaves.
	```java
	String str3 = "Good";
	String str4 = "Good";
	```
	- Em Java, a "pool de strings" permite armazenamento de apenas uma cópia da string na "pool", independentemente de quantas variáveis se referem a mesma sequência.

## **Concatenação de Strings**:

Basta empregar o operador `+` para concatenar duas ou mais strings em uma única. Aqui está um exemplo abaixo:
```java
String str1 = "Hello";
String str2 = "World";
String result = str1 + " " + str2;  /* Result: "Hello World" */
```


### Formatação





