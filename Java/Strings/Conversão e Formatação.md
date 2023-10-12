---
aliases:
  - conversion_java
  - format_java
tags:
  - java
date: 2023-08-31
time: 22:58
complete:
---

# Conversão e Formatação

## $\text{String}\longrightarrow\text{Integer}$

A conversão de strings de quantias numéricas inteiras ou ponto flutuante para strings pode ser feita com [[Classes Empacotadoras|métodos empacotadores]] descritos abaixo:

1. `Integer.parseInt(String intValue)`: Método estático para a conversão de uma string em uma quantia inteira.

```java
String intValue = "100";
int convertedInt = Integer.parseInt(intValue);  /* convertedValue ==> 100 */
```

2. `Double.parseDouble(String doubleValue)`: Método estático para a conversão de uma string em ponto flutuante.

```java
String doubleValue = "3.14";
double doubleValue = Double.parseDouble(doubleValue);  /* doubleValue ==> 3.14 */
```

## $\text{Character}\to \text{Integer}$

1. `Character.getNumericValue(char c)`: Forma estática de converter caracteres em valores numéricos.

```java
int numericValue = Character.getNumericValue('1'); /* numericValue ==> 1 */
```

## $\text{Integer}\longrightarrow\text{String}$

1. `String.valueOf(int value)`:  Forma estática alternativa de converter valores numéricos inteiros ou ponto flutuante para variáveis tipo string.

```java
int numericValue = 12345;
double doubleValue = 3.14;
String convertedValue = String.valueOf(numericValue);  /* convertedValue ==> "12345" */
String convertedDouble = String.valueOf(doubleValue);  /* convertedDouble ==> "3.14" */
```

2. `Integer.toString(int value)`: Forma estática equivalente à anterior para converter quantias numéricas para tipo string por meio da wrapper class `Integer`. No entanto, como a classe empacotadora é de inteiros, não é possível converter quantias em ponto flutuante.

```java
Integer integerValue = 9999;
String convertedValue = Integer.toString(integerValue);  /* integerValue ==> "9999" */
String convertedInt = Integer.toString(1234);  /* convertedInt ==> "1234" */
```

3. `String str = "" + value`: É possível empregar a concatenação de strings para converter valores inteiros ou em ponto flutuante para a cadeia de caracteres.

```java
int intValue = 1234;
double doubleValue = 12.34;
String convertedInt = "" + intValue;       /* convertedInt ==> "1234" */
String convertedDouble = "" + doubleValue  /* convertedDouble ==> "12.34" */
```

## $\text{Format: \texttt{"\%d \%c", num, char)..}}$

Por outro lado, a formatação para a entrada de uma string pode ser feita da seguinte forma:

1. `String.format()`: Permite formatar a entrada de uma string por meio de [[Código de Formatação|codificação]] de formato semelhante à C.