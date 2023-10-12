---
alias: namespace
tags: ⓒ＋＋ py
date: 2023-07-26
time: 20:33
---

# Namespaces

> $\textit{Definição.}$ Mecanismo utilizado para organizar e gerenciar o escopo de nomes em um programa.

Corresponde a um contêiner lógico que agrupa identificadores (nome de variáveis, funções, classes ou outras entidades) para evitar conflitos de nome.

> [!note] Definição de Namespaces C++
> Exemplo em da definição do namespace `pessoal` e uso de suas declarações.
> ```c
> namespace pessoal {
> 	int valor = 1;
> 	void imprimir_valor() {
> 		std::cout << "o valor é " << valor << std::endl;
> 	}
> }
> int valor = 0;
> 
> /* Imprime "o valor é 1" */
> std::cout << "o valor é " << pessoal::valor << std::endl;   
> /* Imprime "o valor é 0" */
>  pessoal::imprimir_valor();  
> ```

> [!note] Definição de Namespaces Python
> Exemplo da definição de dois namespaces `modulo1` e `modulo2`.
> ```py
> # Módulo 1
> def saudacao():
> 	return "Olá do Módulo 1"
> 
> # Módulo 2
> def saudacao():
>     return "Olá do Módulo 2"
> 
> # No código principal
> import modulo1
> import modulo2
> 
> print(modulo1.saudacao())  # Saída: "Olá do Módulo 1"
> print(modulo2.saudacao())  # Saída: "Olá do Módulo 2"
> 
> ```
