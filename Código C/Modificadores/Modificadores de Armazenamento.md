---
alias: armazenamento
tags: ⓒ/modificadores
date: 2023-07-21
time: 00:50
---

# Modificadores de Armazenamento

> $\textit{Definição.}$ Indicam a forma como as [[Código C/Conceitos Gerais/Variáveis| variáveis]] devem ser armazenadas, havendo 4 principais modos.

Os 4 principais modos de armazenamento são:
- `auto`: Modificador de armazenamento padrão (não é útil), define uma variável como local.
-  **Ex.** Declaração de um inteiro na função principal `int var`.

- `extern`: Indica que uma variável foi definida em outro arquivo-fonte, permite acesso de variáveis globais de outro arquivo
 - **Ex.** A variável global `gbl` foi declarada em outro arquivo.
	```c
	extern int gbl;
	
	printf("Valor da variável global: %d\n", gbl);    /* Em uma função do programa */
	/* restante do programa ... */
	```

- `static`: Indica que uma variável mantém seu valor entre as chamadas de funções e, assim, seu valor não é reinicializado na próxima chamada.
- **Ex.** Suponha a função `sum` com uma variável estática contadora `cont`.
	```c
	void sum() {
		static int cont = 0;
		printf("Contador: %d\n", cont++);
	}
	```

- `register`: Indica ao registrador que a variável pode ser armazenada em um registrador do processador, facilitando sua otimização.
- **Ex.** Suponha a função `count` com uma variável register `cont`.
	```c
	void count(int size) {
		register cont;
			for (cont = 0; cont < size; ++cont)
				printf("Contador: %d\n", cont);
	}
	```

Diferenças entre os modificadores `auto` e `static`:

|`static`|Inicializa com zero|Inicialização não envolve variáveis|Iniciada uma vez|
|:--|--|--|--|
|`auto`|**Sem inicialização implícita**|**Inicialização pode envolve variáveis**|**Iniciada + uma vez**|


