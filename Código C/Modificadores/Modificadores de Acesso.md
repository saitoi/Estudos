---
alias: acesso
tags: C/modificadores
date: 2023-07-23
time: 11:44
---

# Modificadores de Acesso

> $\textit{Definição.}$ Determina o modo como as [[Código C/Conceitos Gerais/Variáveis|variáveis]] podem ser acessadas, indicando se elas podem ser modificadas ou não, por exemplo.

Os $3$ principais modos de acesso são:
- `const`: Empregado para declarar uma constante, isto é, não podem ser modificadas no decorrer da execução do programa.
- **Ex.**  Suponha a declaração da constante `pi`.
	```c
	const int pi = 3.14;
	```

- `volatile`: Indica ao compilador que a variável pode ser alterada por eventos externos e, assim, não poderá ser feita uma otimização, por exemplo.

- `restrict`: Empregado para ponteiros, indicando ao compilador que aquilo que o ponteiro aponta não é apontado por nenhuma outra variável.

> [!note] Constantes e ponteiros
> Devemos nos atentar para a diferença entre ponteiro que armazena endereço para valor constante e ponteiros constantes para endereços modificáveis. 
> 
> Representação em código:
> ```c
> const int ptr1;   /* Ponteiro armazena endereço para valor constante */
> const int ptr2;   /* Ponteiro constante que armazena endereço para valor */ 
> ```
