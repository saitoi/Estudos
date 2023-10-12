---
alias: pointer
tags: ⓒ/pointer
---

# Ponteiros

> $\textit{Definição.}$ Variável especial que armazena o endereço de memória de outra variável, permitindo acessar e modificar uma localização específica da memória.

- Ex. `*pont`
	-  Operador `*` indica conteúdo apontado por um endereço de memória.
	- `pont` armazena o endereço de memória em si.

Ordem de alteração do conteúdo em ponteiros:
```c
/* Inteiros e outros */
int i = 10, *pont;
pont = &i;                             /* "pont" recebe endereço de "i" */
printf("Valor de i é %d\n", *pont);    /* Valor de i é 10 */

/* Char e strings */
char *c = "Hello, World";              /* Não é necessário receber endereço */
printf("%s", c);                       /* "Hello, World" */
```

## Operações não previstas ponteiros

> $\textit{Definição.}$ Refere-se a situações em que o programa tenta alocar/modificar áreas da memória além do que foi previamente alocado/permitido.

Suponha as seguintes variáveis:
```c
int i, j;
int *pi = &i, *pj = &j;
```

- Adição de dois ponteiros
```c
pi += pj;    /* Soma de dois endereços */
```

- Operador desreferenciamento `*` no lugar incorreto
```c
i = &*&j     /* "i" recebe endereço */
i = *&*j     /* Operador "*" seguido da variável */
```

## Operações Válidas

Diferença entre ponteiros
```c
i = pi - pj;    /* Calcula a distância na memória entre 2 endereços */
```

Acessa posições em um vetor
```c
*(arr+i)        /* Acessa uma posição qualquer do vetor "arr[]" */
```
