---
aliases:
  - variaveis_java primitivos
tags:
  - java
date: 2023-08-07
time: 19:58
complete:
---

# Variáveis e Primitivos

> $\textit{Definição.}$ Semelhante à definição anterior de [[Código C/Conceitos Gerais/Variáveis#^a9f1d1|variáveis]], se tratam de espaços de memória nomeados que armazenam dados, como números, texto ou objetos. 

**Obs.** Variáveis declaradas em classes são denominadas de **campos** ou **atributos**.

$\texttt{Tipos primitivos}$: Blocos de construção fundamentais para representar e armazenar tipos de dados simples em um programa. Aqui está uma tabela descrevendo cada tipo primitivo:

|Primitivos|Descrição|
|---|---|
|`int`|Tipo de dado inteiro usado para armazenar valores inteiros.|
|`float`|Tipo de dado de ponto flutuante de precisão simples usado para armazenar números com parte decimal.|
|`double`|Tipo de dado de ponto flutuante de precisão dupla usado para armazenar números com parte decimal.|
|`char`|Tipo de dado para armazenar caracteres individuais, como letras e símbolos.|
|`boolean`|Tipo de dado booleano que representa valores verdadeiro ou falso.|
|`short`|Tipo de dado inteiro de 16 bits usado para armazenar valores inteiros em um intervalo maior que `byte`.|
|`long`|Tipo de dado inteiro de 64 bits usado para armazenar valores inteiros grandes.|
|`byte`|Tipo de dado inteiro de 8 bits usado para armazenar valores pequenos.|

Tipos adicionais em Java:

|Tipos|Descrição|
|---|---|
|`String`|Armazena sequências de caracteres, como palavras ou frases.|
|`BigDecimal`|Permite a representação de números em ponto flutuante com precisão arbitrária.|
|`Arrays`|Coleções de elementos do mesmo tipo, armazenados sequencialmente na memória.|
|`Object`|A classe base de todos os tipos de objetos em Java, podendo armazenar qualquer tipo de dado.|
|`Wrapper Classes`|Conjunto de classes para os primitivos serem tratados como objetos, definido em [[Classes Empacotadoras\|wrapper classes]].|
|`Classes`|[[Classes]] definidas pelo usuário ou externamente.|

> [!info] Case Sensitive
> A linguagem Java é "case sensitive", isto é, diferencia entre palavras maiúsculas e minúsculas. Isso inclui palavras-chaves, sintaxe da linguagem, nomes de variáveis, tipos de datas, dentre outros.

## $\texttt{Inicialização implícita}$

A linguagem Java realiza a inicialização implícita para variáveis com um valor da padrão com exceção de variáveis locais. Aqui está uma tabela indicando os valores padrões:
 
| Tipo de Dado | Valor Padrão    |
| ------------ | --------------- |
| `int`        | 0               |
| `short`      | 0               |
| `long`       | 0L              |
| `byte`       | 0               |
| `float`      | 0.0f            |
| `double`     | 0.0d            |
| `char`       | '\u0000' (nulo) |
| `boolean`    | `false`         |
| `Object`     | `null`          |
| `String`     | `null`          |
| `Arrays`     | `null`          |

**Obs.** Variáveis primitivas nunca serão inicializadas com `null`.

## $\texttt{Declaração}$

> [!info] Legibilidade
> Para auxiliar na legibilidade do código, podemos usar o caractere sublinhado `_` para separar as casas decimais, tal como por exemplo:
> ```java
> int UmMilhao = 1_000_000;
> ```

