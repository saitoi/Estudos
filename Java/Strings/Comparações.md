---
aliases:
  - comparacao_string
tags:
  - java
  - ⓒ
date: 2023-08-31
time: 15:51
---

# Comparações

Para realizar a comparação de objetos do tipo `String`, existem duas formas:

1. **Comparação com operador `==`**
	- Ao utilizar esse operador, são comparados os endereços de memória das strings, não seus conteúdos. É verificada se a referência das variáveis apontam para o mesmo objeto.
	- Sintaxe: `(x == y);`

2. **Comparação com método `.equals()`**
	- Ao empregar esse [[Subclasses#^00b50c|método da classe Object]], o conteúdo das strings são comparados entre si, não seus endereços. O método retorna um booleano, isto é, $1$ ou $0$.
	- Sintaxe: `(x.equals(y));`

A comparação lexicográfica de strings, tal como a função `strcmp()` é feita da seguinte forma:

1. `.compareTo(String str)`: Realiza a comparação de strings segundo a ordem alfabética e diferencia letras maiúsculas de minúsculas segundo a posição na codificação Unicode.

```java
String str1 = "abc";
String str2 = "def";

int result = str1.compareTo(str2);
if (result > 0) {
	System.out.println("str1 vem antes de str2.");  /* Isso vai ser impresso. */
} else if (result < 0) {
	System.out.println("str2 vem antes de str1.");
} else {
	System.out.println("str1 e str2 são idênticas.");	
}
```

Para ignorar as diferenças entre os caracteres maiúsculos e minúsculos, podemos empregar o método abaixo:

1. `.compareToIgnoreCase(String str)`: Assim como o método anterior, realiza a comparação alfabética das strings descartando as diferenças entre letras maiúsculas e minúsculas.

```java
String str1 = "abc";
String str2 = "ABC";

int result = str1.compareTo(str2);
if (result > 0) {
	System.out.println("str1 vem antes de str2.");  
} else if (result < 0) {
	System.out.println("str2 vem antes de str1.");
} else {
	System.out.println("str1 e str2 são idênticas.");	/* Isso vai ser impresso. */
}
```
```