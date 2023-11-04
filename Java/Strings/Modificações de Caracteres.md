---
alias: upper_case lower_case
tags: java
date: 2023-08-31
time: 20:32
---

# Modificações de Caracteres

A conversão para caracteres maiúsculos ou minúsculo, bem como a substituição de certos caracteres na string pode ser feita pelos seguintes métodos:

1. `.toUpperCase()`: Converte todos os caracteres da string para maiúsculo, tal como no exemplo abaixo:

```java
String word = "upper_case";
word = word.toUpperCase();
System.out.println("New word: " + word);  /* "New word: UPPER_CASE" */
```

2. `.toLowerCase()`: Converte todos os caracteres da string para minúsculo, tal como abaixo:

```java
String word = "LOWER_CASE";
word = word.toLowerCase();
System.out.println("New word: " + word);  /* "New word: lower_case" */
```

3. `.replace(char oldChar, char newChar)`: Converte todos os caracteres do tipo `oldChar` para `newChar` na string. Observe o exemplo abaixo:

```java
String replaced = "C  ";
replaced = replaced.replace(' ', '+');
System.out.println("My program is " + replaced);  /* "My program is C++" */
```

4. `.replaceAll(String regex, String replacement)`: Converte todas as ocorrências da string `regex` para `replacement`. Observe o exemplo abaixo:

```java
String food = "french potato";
food = food.replaceAll("potato", "fries");
System.out.println("I'm eating " + food);  /* "I'm eating french fries" */
```

5. `trim()`: Realiza a remoção dos espaços em branco no início e no final da string, tal como abaixo:

```java
String blank = " Hello ";
System.out.println("Before: (" + blank + ")");
System.out.println("After: (" + blank.trim() + ")");
/* Before: ( Hello )
   After: (Hello)    */
```
