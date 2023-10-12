---
aliases:
  - split
  - join
tags:
  - java/strings
date: 2023-08-31
time: 22:06
complete:
---

# Divisão e Junção

A criação de substrings pode ser feita de formas distintas das demonstradas na seção de [[Substrings]]. Aqui estão alguns métodos:

1. `.split(String regex)`: Divide a string com base no delimitador ou string `regex` escolhida.

```java
String date = "30/10/2004";
String[] information = date.split("/");
for (String data : information) {
	System.out.println(data);
}  
/*
	30
	10
	2004
*/
```

2. `.join(CharSequence delimiter, CharSequence elements)`: Junta as substrings de um objeto do tipo `String[]` ou string para string por meio de um delimitador selecionado, tal como abaixo:

```java
String[] fruits = {"apple", "banana", "orange"};
String result = String.join(", ", fruits);
System.out.println(result);  /* "apple, banana, orange" */
```
