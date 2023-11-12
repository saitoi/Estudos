---
aliases:
  - comparacao_string
tags:
  - java
  - C
date: 2023-08-31
time: 15:51
---

# Comparações

Para realizar a comparação de dois objetos quaisquer em Java, podemos realizar isso de duas formas.

1. **Operador `==`**
	- O operador `==` é responsável pela comparação da **referência/endereço** dos objetos na memória, ou seja, é avaliado se os dois objetos comparados estão apontando para o mesmo endereço na memória.
1. **Método `equals()`**
	- O método `equals()`, pertencente à superclasse `Object` de Java, adiciona verificações a mais em relação ao operador `==` mencionado anteriormente. Essas validações são normalmente implementadas para a classe `String`, `Integer`, dentre outras [[Classes Empacotadoras|empacotadoras]]. Com efeito, podemos sobrescreve-lo caso desejarmos adicionar alguma inspeção extra.

## $\texttt{Comparações em Strings.}$

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