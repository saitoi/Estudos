---
alias: processador
tags: ⓒ ⓒ＋＋
date: 2023-07-24
time: 01:00
---

# Pré-Processador

> $\textit{Definição.}$ Etapa importante que antecede o processo de compilação de programas (C/C++) em que são realizadas algumas transformações e substituições no código segundo as diretivas do pré-processador.

As diretivas do processador iniciam com o caractere `#`, tratando-se de instruções para indicar o próximo passo ao pré-processador. As principais diretivas são:

|Diretiva|Descrição|
|---|---|
|`#include`|Empregada para incluir o conteúdo de outros arquivos no programa, sendo implementada para incluir arquivos de cabeçalhos (header files).|
|`#define`|Empregada para definir macros no código, isto é, identificadores que representam um valor ou uma sequência de códigos. Quando a macro é encontrada, o pré-processador a substitui pelo seu valor correspondente.|
|`#ifdef`, `#ifndef`, `#else` e `#endif`|Utilizadas para criar blocos condicionais no código, isto é, para caso a macro estiver definida ou não.|
|`#if`, `#elif` e `#endif`|Permitem realizar avaliações condicionais mais complexas, verificando expressões que contenham macros ou valores constantes e incluir ou excluir blocos com base nessa análise.|
|`#undef`|Empregada para remover a definição de uma macro previamente definida com `#define`. A sintaxe é simples `#undef nome_macro`.|

> [!example]
> <ins>Comando `#ifdef` (If Defined)</ins>: Verifica se uma macro foi definida anteriormente e, caso positivo, um bloco de comando será executado no lugar do outro, tal como no **exemplo abaixo:**
> ```c
> #ifdef nome_macro
> // Código a ser executado se a macro estiver definida
> #else
> // Código a ser executado se a macro NÃO estiver definida
> #endif
> ```
> <ins>Comando `#ifndef` (If Not Defined)</ins>: Semelhante ao comando anterior, no entanto é feita a verificação da não existência da macro, como **por exemplo**:
> ```c
> #ifndef nome_macro
> // Código a ser executado se a macro NÃO estiver definida
> #else
> // Código a ser executado se a macro estiver definida
> #endif
> ```
> <ins>Comando `#if`</ins>: Realiza uma avaliação condicional em relação a uma expressão que envolve macros definidas anteriormente ou valores constantes. Portanto, se a expressão for verdadeira um dos blocos será executado e vice-versa, aqui está um **exemplo**:
> ```c
> #define DEBUG 1
>
> #if DEGUB
> // Este bloco será incluído na compilação, pois DEBUG é verdadeiro
> #else
> // Este bloco será ignorado na compilação, pois DEBUG é verdadeiro
> #endif
> ```
> <ins>Comando `#elif` (Else If)</ins>: Empregada juntamente da diretiva anterior para criar condições alternativas adicionais dentro de um mesmo bloco, considere um **exemplo semelhante ao anterior**:
> ```c
> #define DEBUG 2
> 
> #if DEBUG == 1
>     printf("Nível de debug 1\n");
> #elif DEBUG == 2
>     printf("Nível de debug 2\n");    // Este bloco será executado, pois DEBUG é 2
> #elif DEBUG == 3
>     printf("Nível de debug 3\n");
> ```

Algumas diretivas adicionais estão descritas abaixo:

|Diretiva|Descrição|
|---|---|
|`#error`|Utilizada para gerar erros no pré-processamento, exibindo uma mensagem de erro especificada pelo usuário. Pode estar contida em algum bloco da diretiva `#if`/`#endif`.|
|`#line`|Empregada para alterar o número da linha do código-fonte que está sendo processado pelo pré-processador. Permite simular estar em uma linha ou arquivo especificados pelo usuário. A sintaxe é: `#line numero_linha "nome_arquivo"`.|
|`#pragma`|Fornece instruções específicas ao compilador/pré-processador, frequentemente empregado para ativar/desativar extensões específicas do compilador ou para configurar opções específicas do compilador.|

> [!example]
> <ins>Exemplo Comando `#error` (Erro).</ins>
> ```c
> #define TAMANHO_MAXIMO 150
> 
> #if TAMANHO_MAXIMO > 100
> #error O tamanho máximo não pode ser maior que 100!
> #endif
> ```
> Nesse caso, a mensagem de erro será exibida e o programa não será compilado.
> 
> <ins>Exemplo Comando `#line` (Linha).</ins>
> ```c
> int x = 10; int y = 20;
> 
> #line 100 "outro_arquivo.c"
> printf("Valores: x = %d, y = %d\n", x, y);
> ```
> No trecho anterior, o programa simulará o código abaixo do comando `#line` como pertencente à linha $100$ do programa `outro_arquivo.c`. Desse modo, caso tivermos algum erro, o programa indicará a mensagem de erro como estando naquele ponto do arquivo citado.
> 
> <ins>Exemplo Comando `#pragma`.</ins>
> ```c
> #pragma warning(disable: 4996)
> 
> int main() {
> 	char str[] = "Exemplo de uso de #pragma";
> 	std::cout << str << std::endl;
> 	
> 	return 0;
> }
> ```
> No caso anterior, utilizamos a diretiva `#pragma` para desativar o erro de compilação $4996$ atrelado à utilização de funções inseguras, como é o caso do `cout << str << ..`
> 



