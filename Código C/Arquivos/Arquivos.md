---
aliases:
  - files_c fluxos
tags:
  - ⓒ
date: 2023-07-23
time: 04:06
complete:
---

# Arquivos

> $\textit{Definição.}$ Permitem o armazenamento de dados de forma persistente e o registro de informações em dispositivos de armazenamento.

Programas se comunicam com arquivos por meio dos fluxos e, portanto, para que um arquivo em um periférico esteja associado a um fluxo é necessário que ele seja aberto, por meio de [[Operações com Arquivos | operações com arquivos]].


## Fluxos de Texto

> $\textit{Definição.}$ Refere-se à leitura e gravação de caracteres em um arquivo, os quais são separados em linhas terminadas por um caractere final de linha.

Principais fluxos de textos em C:
- `stdin`: Fluxo de entrada padrão que recebe os dados de entrada do usuário, atrelado ao teclado. Emprega funções para a leitura, tal como `scanf`.
- `stdout`: Fluxo de saída padrão que exibe os resultados, atrelado ao monitor. Emprega funções para a gravação, tal como `printf`.
- `stderr`: Fluxo de saída erro padrão empregado para imprimir mensagens de erro, atrelado ao monitor. Utiliza funções para a gravação de erros, tal como `fprintf`.

## Fluxo Binário

> $\textit{Definição.}$ Refere-se à leitura e escrita de dados em arquivos binários, isto é, uma sequência de bytes contidos em um dispositivo externo.

**Principais funções:**

- `size_t fread(void *ptr, size_t size, size_t nmemb, FILE *file)`
	- Função empregada para ler blocos de dados binários em um fluxo, retornando o número de caracteres lidos com êxito.
	- **Ex.** Desejamos ler um inteiro para a variável `var` de um arquivo binário `.bin`.
	```c
	fread(var, sizeof(int), 1, arquivo);
	```

- `size_t fwrite(const void *ptr, size_t size, size_t nmemb, FILE *file)`
	- Função empregada para escrever blocos de dados binários em um arquivo externo, retornando 
	- **Ex.** Desejamos inserir os dados da estrutura `node1` em um arquivo `.bin`.
	```c
	fwrite(&node1, sizeof(struct Node), 1, arquivo);
	```
