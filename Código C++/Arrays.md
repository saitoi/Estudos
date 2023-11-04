---
aliases:
  - arrays_C_Cpp
tags:
  - C＋＋
  - C
date: 2023-08-03
time: 21:13
---

# Arrays

> $\textit{Def. Arrays.}$ Estrutura de dados estática que representa uma coleção de elementos de um mesmo tipo, armazenados de forma contígua na memória.

- Elementos individuais são acessíveis individualmente pela posição/indexo, de modo que o primeiro elemento está na posição $0$ e o último se encontra em $n-1$.
- Todos os elementos são inicializados e não é possível verificar se está fora dos limites do array.
- Iterações ou "*loopings*" são usados para processar arrays.

### Declaração

Sintaxe básica: `tipo_elemento `.

### Exemplos

```cpp
int array[5];                       /* Declarando um array de inteiros com tamanho fixo de 5 */
char nome[] = "Pedro";              /* Declarando um array de caracteres com tamanho 5 */
float notas[] = {97.5, 10.0, 8.7};  /* Declarando um vetor ponto flutuante com tamanho 3 */
```
