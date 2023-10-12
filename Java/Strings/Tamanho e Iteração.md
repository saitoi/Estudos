---
alias: null
tags: java
date: 2023-08-31
time: 16:05
---

# Tamanho e Iteração

As funções para a determinação do tamanho e características de strings está descrita abaixo:

1. `.length()`: Retorna um inteiro equivalente ao número de caracteres da string. Exemplo do retorno do número de caracteres do meu nome:

```java
String nome = "Pedro Saito";
System.out.println("O nome possui " + nome.length + " caracteres.");  /* "O nome possui 11 caracteres" */
```

2. `.isEmpty()`: Verifica se a string está vazia, isto é, equivale a `""` e retorna um booleano correspondente. Exemplo da verificação para a string vazia ou não:

```java
String palavra = "";
if (palavra.isEmpty())
	System.out.println("A string está vazia.");
else
	System.out.println("A string não está vazia.");
```

3. `.charAtIndex(int index)`: Retorna o caractere da posição especificada, semelhante à indexação `str[i]`. Aqui está um exemplo alterando o último caractere da string `"garoto"`:

```java
String genero = "garoto";
genero.charAtIndex(genero.length() - 1) = 'a';
System.out.println("Genero: " + genero);  /* "Genero: garota" */
```

4. `.indexOf(String str)`: Retorna o índice da primeira ocorrência da substring, semelhante à função `char *strstr()`.

```java
String estado = "infeliz";
int id = estado.indexOf("feliz");
System.out.println("O índice de \"feliz\" em \"infeliz\" é " + id);
```
