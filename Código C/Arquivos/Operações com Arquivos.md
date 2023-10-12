---
aliases:
  - files_operation_C
tags:
  - ⓒ/✖
date: 2023-07-25
time: 09:35
complete:
---

# Operações com Arquivos

Para acessarmos um arquivo, é necessário definir um ponteiro especial `FILE`, tal como em: `FILE *file`.
Principais funções para operação em arquivos:

1. `FILE *fopen(const char *parq, const chat *modo)`
	- Função destinada para abrir arquivos.
	- A sintaxe inicia com o parâmetro do arquivo a ser aberto e termina com o modo de abertura.

2. `int fprintf(FILE *stream, const char *format, ...)`
	- Função empregada para imprimir dados formatados em um arquivo.
	- A sintaxe é semelhante à `printf`, no entanto adicionamos o arquivo destino como primeiro parâmetro.
	- Retorna o número de caracteres impressos com sucesso ou um valor negativo caso houver erro na impressão.

3. `int fscanf(FILE *stream, const char *format, ...)`
	- Função empregada para ler dados formatados de um arquivo.
	- A sintaxe é semelhante à `scanf`, no entanto adicionamos o arquivo destino como primeiro parâmetro.
	- Retorna o número de caracteres lidos com sucesso ou um valor negativo caso houver erro na leitura.

4. `int fclose(FILE *stream)`
	- Função empregada para fechar o arquivo que foi previamente aberto com `fopen`.
	- A sintaxe se resume ao arquivo a ser fechado.
	- Retorna $0$ caso o fechamento foi bem sucedido e diferente de zero

> [!info] Modos de Abertura 
> 
> | Modos de Abertura | Utilidade | Funções | Adicional |
> |:-:|-|-|-|-|
> | `"r"` | Leitura | `fscanf` | Arquivo deve existir, não é sobrescrito |
> | `"w"` | Escrita | `fprintf` | Arquivo não precisa existir, é sobrescrito |
> | `"a"` | Escrita | `fprintf` | Arquivo não precisa existir, adiciona ao final |
> | `"r+"` | Leitura e Escrita | `fscanf` e `fprintf` | Arquivo deve existir, é sobrescrito |
> | `"w+"` | Leitura e Escrita | `fscanf` e `fprintf` | Arquivo não precisa existir, é sobrescrito |
> | `"a+"` | Leitura e Escrita | `fscanf` e `fprintf` | Arquivo não precisa existir, adiciona ao final |

