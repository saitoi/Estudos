---
alias: dinamic allocation alocação
tags: C/pointer
date: 2023-07-20
time: 19:41
---

# Alocação Dinâmica

> $\textit{Definição.}$ Recurso que permite reservar/liberar blocos de memória no decorrer da execução do programa.

As principais funções manipulação da memória estão contidas na [[Python/Bibliotecas#^1a8085| biblioteca]] `stdlib.h` e serão descritas abaixo:

1. `void *malloc(size_t size)`: Aloca uma quantidade específica de memória no decorrer da execução do programa.
	- **Ex.** Suponha que desejamos alocar um vetor de $2$ inteiros para `var`.
	```c
	int *var;
	var = (int *) malloc(sizeof(int) * 2);
	```

2. `void *calloc(size_t num_elements, size_t element_size)`: Mesma funcionalidade que o `malloc`, no entanto inicializa os bytes alocados para $0$.
	- **Ex.** Suponha que desejamos alocar uma string de $4$ caracteres para `str`.
	```c
	char *str;
	str = (char *) calloc(4, sizeof(char));
	```

3. `void *realloc(void *ptr, size_t size)`: Empregada para realocar memória previamente alocada com `malloc` ou `calloc`, sendo utilizada para aumentar/diminuir o tamanho da memória alocada.
	- **Ex.** Suponha que desejamos realocar mais $2$ posições de memória para a variável `var` do primeiro exemplo.
	```c
	novo_var = (int *) realloc(var, sizeof(int) * 4)
	var = novo_var;
	```

4. `void free(void *ptr)`: Usada para liberar memória alocada anteriormente.
	- **Ex.** Suponha que desejamos liberar a memória alocada de `var`.
	```c
	free(var);
	```

**Comando `new`**
- 