---
alias: variaveis_C_Cpp
tags: C C＋＋
---

# Variáveis

> $\textit{Definição.}$ Representa um local na memória reservado para armazenar um valor.
^a9f1d1

Possuem três atributos principais:
-  **Tipo de dado**: Tipo da variável, define o que ela pode armazenar e cada tipo possui tamanhos distintos.
- **Nome da variável**: Identificador único da variável para acessá-la/referenciá-la.
-  **Valor**: Conteúdo armazenado pela variável, podendo ser modificado.

Tabela Válida para a linguagem C:

|Tipos|Descrição|
|---|---|
|`int`|Armazenam números inteiros (positivos e negativos) com intervalo de valores de 32 bits.|
|`long`|Tipo de dado inteiro com tamanho maior que `int`. Geralmente ocupa 4 bytes em sistemas de 32 bits e 8 bytes em sistemas de 64 bits.|
|`short`|Tipo de dado inteiro curto. Ocupa 2 bytes.|
|`unsigned int`|Tipo de dado inteiro sem sinal que armazena apenas valores não negativos. Geralmente ocupa 4 bytes.|
|`unsigned long`|Tipo de dado inteiro sem sinal de tamanho maior que `unsigned int`.|
|`unsigned short`|Tipo de dado inteiro curto sem sinal. Ocupa 2 bytes.|
|`long long`|Tipo de dado inteiro com tamanho maior que `long`. Ocupa 8 bytes em sistemas de 32 bits e 8 bytes em sistemas de 64 bits.|
|`unsigned long long`|Tipo de dado inteiro sem sinal com tamanho maior que `unsigned long`.|
|`float`|Armazenam valores decimais (positivos e negativos) com precisão simples (4 bytes).|
|`double`|Armazenam valores decimais com precisão dupla (dobro do float = 8 bytes).|
|`char`|Armazenam caracteres individuais, como letras e símbolos descritos na [[Tabela ASCII]].|
|`char str[]`|Representam [[Código C/Conceitos Gerais/Strings|strings]] que armazenam uma sequência de caracteres (char).|
|`bool`|Representam valores verdadeiros (não zero) ou falsos (0), possuindo 1 bit e definidos pela [[Código C/Conceitos Gerais/Bibliotecas#^de90ff|biblioteca]] `stdbool.h`.|
|`struct`|As [[Structs\|structs]] são tipos definidos pelo usuário, que podem armazenar outros tipos.|
|`typedef`|Modifica o identificador dos tipos das variáveis para nomes definidos pelo usuário.|
|`Arrays`|Coleções de elementos do mesmo tipo, armazenados sequencialmente na memória.|
|`Matrix`|Coleções de vetores dispostos de forma bidimensional/tridimensional.|
|`Pointer`|[[Ponteiros]] declarados com `*`, que podem armazenar o endereço de qualquer variável.|

Variáveis adicionadas em C++:

|Tipos|Descrição|
|---|---|
|`string`|Tipo de dado para armazenar sequências de caracteres (strings). Não é um tipo fundamental, mas uma classe da biblioteca padrão.|
|`wchar_t`|Tipo de dado que armazena um caractere wide (utilizado para suportar caracteres unicode).|

> [!info]
> Cada variável possui um tamanho em bytes de modo que seu intervalo de valores pode ser encontrado na tabela
> descrito na tabela do [[Código C/Tabelas/Tamanho dos Tipos|tamanho dos tipos]].

**Globais:** 
- Variáveis com escopo

**Constantes:**
- `const`: Espaços de memória cujo valor não pode ser modificado após inicialização.

## Declaração de variáveis

1. Nome de variáveis deve começar com letras (Maiúsculas/ Minúsculas) ou sublinhado `_` .
2. Evitar palavras reservadas, tal como `int`, `while`, dentre outras.
3. Variáveis com maiúscula e minúscula são diferentes entre si, "case sensitive".

## Inicializações

1. Operador de atribuição:
```c
int valor = 1;    /* Inicialização estilo C */
```

2. Estilo construtor:
```cpp
int valor (1);    /* Inicialização estilo C++ (POO) */
```

3. Estilo C++ 11:
```cpp
int valor {1};    /* Inicialização estilo C++ 11 */
string 
```