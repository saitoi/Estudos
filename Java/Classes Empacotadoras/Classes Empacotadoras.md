---
aliases:
  - wrapper_classes
tags:
  - java/✖
  - java/classe
date: 2023-08-08
time: 11:33
complete:
---

# Classes Empacotadoras

> $\textit{Definição.}$ Conjunto de classes que permitem que tipos de [[Variáveis e Primitivos|dados primitivos]] sejam tratados como objetos.

A correspondência entre cada tipo primitivo e  sua classe empacotadora segue abaixo:

|Primitivos|Wrapper Class|
|---|---|
|int|Integer|
|double|Double|
|boolean|Boolean|
|char|Character|
|byte|Byte|
|short|Short|
|long|Long|
|float|Float|

> [!info] Comando `new`
> A utilização do comando `new` para criação de objetos de classes empacotadoras é opcional e, portanto, é possível atribuir diretamente um conteúdo a uma variável de uma wrapper class, tal como será feito abaixo:
> ```java
> /* -------- Comando new -------- */
> Integer numeroInteiro = new Integer(42);
> Double numeroDecimal = new Double(3.14);
> Boolean verdadeiro = new Boolean(true);
> Character caractere = new Character('A');
> 
> /* -------- Diretamente -------- */
> Integer valorInteiro = 42;
> Double valorDecimal = 2.17; 
> Boolean falso = false;
> Character caracteres = 'B';
> ```

## $\texttt{Métodos gerais}$



## <span style="color:#ff0000">Isso embaixo precisa ser reformulado:</span>

### Diferença entre tipos primitivos e suas Wrapper Classes

A diferença está na forma como os dados são tratados e nas funcionalidades disponíveis para cada um. Utilizaremos o tipo `int` para exemplificar as diferenças.

1. **Valores nulos**
	- O tipo primitivo `int` não pode armazenar um valor nulo e, portanto, ele sempre terá um valor numérico mesmo que seja zero.
	- Por outro lado, o tipo `Integer` pode assumir um valor nulo, tal como `null`.

2. **Métodos e funcionalidades**
	- Os tipos primitivos não possuem métodos (funções) associados a eles. Assim sendo, o tipo `int` não possui métodos associados.
	- No entanto, as classes empacotadoras possuem métodos associados. Posto isso, podemos chamar por exemplo `toString()` ou `parseInt()` para objetos do tipo `Integer`.

3. **Autoboxing e unboxing**
	- <ins>Autoboxing</ins> refere-se ao processo automático de conversão de um tipo primitivo em sua classe empacotadora correspondente. Por outro lado, <ins>unboxing</ins> é o processo oposto de conversão de um objeto da classe empacotadora para o tipo primitivo.

4. ...

### Máximos e Mínimos

Os valores máximos e mínimos de cada classe empacotadora podem ser obtidos pela sintaxe `classe.MAX_VALUE` e `classe.MIN_VALUE`, respectivamente. Tal como no exemplo abaixo:
```java
System.out.print("O tamanho máximo de um inteiro é " + Integer.MAX_VALUE);
System.out.print("O tamanho mínimo de um byte é " + Byte.MIN_VALUE);
```

### Tamanho de Variáveis

Por outro lado, o número de bits armazenado por cada tipo primitivo de variável pode ser consultado pela sintaxe `classe.SIZE`, tal como no exemplo abaixo:

```java
System.out.print("O número de bytes de um short é " + Short.SIZE);
System.out.print("O número de bytes de um char é " + Character.SIZE);
```

Pode-se consultar os tamanhos máximos e mínimos, bem como o número de bits de cada variável na tabela do [[Java/Tabelas/Tamanho dos Tipos|tamanho dos tipos]].

