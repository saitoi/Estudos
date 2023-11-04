---
alias: strings_C
tags: C C＋＋
---

# Strings

> $\textit{Definição.}$ Sequência de caracteres armazenada em uma área de memória contígua e terminada por um caractere nulo (`0`), sendo representada como um array de caracteres.

Opções para declaração de *strings*:
-  `char str[TAM] = "palavras"`: Definição prévia do tamanho da string.
-  `char str[] = "palavras"`: Tamanho da string ajustado de acordo com palavra.
-  `char *str = "palavras"`: Ajustado conforme palavra, podendo ser realocada. Declarada como [[Ponteiros |ponteiro]] para `char`.

 Formatação da *string* na memória:
- Suponha a declaração: `char str[] = "palavra"`.
- Armazenamento na memória:

|   p   |   a   |   l   |   a   |   v   |   r   |   a   |
|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|
| `[0]` | `[1]` | `[2]` | `[3]` | `[4]` | `[5]` | `[6]` |

## String.h

> $\textit{Definição.}$ Biblioteca padrão do C que fornece funções para a manipulações de *strings*.

 - Principais funções: ^2c716e
	- `size_t strlen(const char *str)`
		- Retorna o tamanho da string `str`, excluindo o caractere nulo de terminação.
			
	 - `char* strcpy(char* destino, const char* origem)`
		- Copia conteúdo da string de origem para a string de destino.
		- `char* strncpy(char *dest, const char *src, size_t n)`
			- Copia $n$ caracteres da string de origem para a de destino.
			
	- `int strcmp(const char* str1, const char* str2)`
		- Compara duas strings e indica a ordem alfabética entre elas.
		- Retorno positivo -  `str1` lexicograficamente maior que `str2`.
		- Retorno negativo -  `str1` lexicograficamente menor que `str2`.
		- Retorno nulo - Strings são idênticas.
		- `int strncmp(const char* str1, const char* str2, size_t n)
			- Compara $n$ caracteres de ambas strings lexicograficamente.
			
	- `char* strcat(char* destino, const char* origem)`
		- Concatena a string de origem no final da string de destino.
			
	- `char* strchr(const char* str, int c)`
		- Procura a primeira ocorrência de um caractere em uma string.
		- Retorna um ponteiro para o caractere.
		- Equivale à função: `strchr()`.
	- 

> [!example] Exemplos das funções
>
> <ins>Exemplo da função `strlen`:</ins> 
> ```c
> char str[] = "palavra";
> int i = strlen(str);    /* i = 8 */
>```
> 
> <ins>Exemplo da função `strcat`:</ins>:
> ```c
> char destino[] = "Hello",
>      origem[] = " world!"; 
>      
> printf("%s", strcat(destino, origem));    /* Hello world! */
> ```
> 
> <ins>Exemplo da função `strcmp`:</ins>
> ```c
> char str1 = "apple",
>      str2 = "banana";
> int result = strcmp(str1, str2);
> 
> if (result < 0)
>     printf("%s vem antes de %s\n", str1, str2);
> else if (result > 0)
>     printf("%s vem depois de %s\n", str1, str2);
> else
>     printf("%s é igual a %s\n", str1, str2);
> ```
