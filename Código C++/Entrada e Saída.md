---
alias: in_out_Cpp
tags: ⓒ＋＋
date: 2023-07-28
time: 19:47
---

# Entrada e Saída

> $\textit{Definição.}$ Refere-se a forma como o programa interage com o usuário, isto é, por meio dos fluxos de entrada (input) e saída (out) padrões.

 A [[Python/Bibliotecas|biblioteca]] `iostream` fornece as funções para a manipulação dos fluxos de entrada e saída. As principais classes envolvidas serão descritas detalhadamente abaixo:

1. **Entrada (E)**
 - `std::cin`: Permite a leitura de valores digitados pelo usuário a partir do teclado.
	 - Ao utilizar esse objeto, empregamos o operador `>>` para atribuição.
	 - Encadeado: `std::cin >> valor1 >> valor2;`.
	 - Gera erro caso o elemento inserido não corresponde ao do programa.
	```cpp
	int valor;
	
	std::cout << "Insira um valor: ";              /* Solicita ao usuário */
	std::cin >> valor;                             /* Recebe o valor */
	std::cout << "O valor inserido foi " << valor; /* Exibe o valor */
	```

2. **Saída (S)**
- `std::cout`: Permite imprimir valores e mensagens no console.
	- Ao utilizar esse objeto, empregamos o operador `<<` para impressão.
	- Encadeado: `std::cout << "O valor é " << valor;`.
	- Não adiciona quebra-linha automaticamente, podemos inserir com `<< "\n"` ou `<< endl`.
	```cpp
	std::cout << "Essa mensagem foi impressa.";
	```
 
- `std::cerr`: Permite imprimir mensagens de erro no console, útil para exibir informações sobre falha no programa.
	- Ao utilizar esse objeto, empregamos o operador `<<` para impressão.
	```cpp
	int divisor = 0;
	if (divisor == 0)
		std::cerr << "Erro: Divisão por zero não é permitida.";
	```

- `std::clog`: Permite imprimir mensagens de log ou informações de depuração do console.
	- Ao utilizar esse objeto, empregamos o operador `<<` para impressão.
	```cpp
	std::clog << "Iniciando o programa." << endl;
	```
