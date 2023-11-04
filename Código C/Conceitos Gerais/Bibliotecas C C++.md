---
aliases:
  - library_C_Cpp
  - biblioteca_C_Cpp
tags:
  - Bibliotecas
  - C
  - C＋＋
date: 2023-07-22
time: 13:37
complete:
---

# Bibliotecas

> $\textit{Definição.}$ Conjunto de funções, constantes e definições que podem ser implementadas no desenvolvimento de programas em C.

## $\text{Principais bibliotecas padrões.}$

| Biblioteca  Padrões C | Descrição                                                                                                                        |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `stdio.h`      | Biblioteca essencial cujo prefixo "stdio" refere-se a "standard input/output" (entrada/saída padrão). Fornece funções <br>  para leitura e gravação de dados na entrada padrão (teclado) e saída padrão (monitor) descritas em [[Entrada e Saída]]. |
| `stdlib.h`     | Contém funções relacionadas à alocação dinâmica de memória e utilização de ponteiros, descritas em [[Ponteiros]]. <br>Também engloba funções para a conversão de strings presentes em [[Conversão de Strings]], e permite a geração de números aleatórios.|
| `string.h`     | Fornece funções para a manipulação de strings e possui uma seção reservada em [[Strings]].                                            |
| `math.h`       | Oferece funções matemáticas comuns, como funções trigonométricas, exponenciação, logaritmos, arredondamento, etc. |
| `limits.h`     | Fornece constantes que representam os limites das variáveis inteiras em um dado sistema.<br> Possui uma seção reservada em [[Código C/Conceitos Gerais/Aproximação\|Limites]]. |
| `ctype.h`      | Contém funções para classificação de caracteres, verificação de letra, dígito, espaço em branco dentre outros. |
| `time.h`       | Fornece funções para trabalhar com datas e horários, permitindo obter o tempo real (`time()`), converter o tempo real <br> em representações de data/horário e calcular a diferença entre datas. |
| `stdbool.h`    | Introduz o tipo de dado booleano em C que representa verdadeiro ou falso (`true` e `false`).                                       |

| Bibliotecas Padrões C++ | Descrição  |
| ------------------------ | --  |
| `iostream`              | Contém classes e objetos para manipular fluxos de entrada e saída padrões, bem como saídas de erro e log. <br> As principais classes envolvidas estão descritas em [[Código C++/Entrada e Saída\|Entrada e Saída]]. |
| `climits`               | Fornece constantes que representam os limites das variáveis inteiras em um dado sistema.<br> Possui uma seção reservada em [[Código C++/Limites\|Limites de C++]]. |
