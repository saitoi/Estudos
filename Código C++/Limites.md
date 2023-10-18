---
alias: limits_Cpp
tags: C＋＋
date: 2023-08-02
time: 15:16
---

# Limites

> $\textit{Definição.}$ Limites de armazenamento de cada tipo de variável, expresso por constantes definidas na [[Código C/Conceitos Gerais/Bibliotecas| biblioteca climits ]].

| Constante        | Descrição                                   | Valor               |
|------------------|---------------------------------------------|---------------------|
| `CHAR_BIT`       | Número de bits em um byte (caractere)       | 8                   |
| `SCHAR_MIN`      | Valor mínimo do tipo `signed char`          | -128                |
| `SCHAR_MAX`      | Valor máximo do tipo `signed char`          | 127                 |
| `UCHAR_MAX`      | Valor máximo do tipo `unsigned char`        | 255                 |
| `CHAR_MIN`       | Valor mínimo do tipo `char`                 | Depende da plataforma (geralmente -128 ou 0) |
| `CHAR_MAX`       | Valor máximo do tipo `char`                 | Depende da plataforma (geralmente 127 ou 255) |
| `SHRT_MIN`       | Valor mínimo do tipo `short int`            | -32768              |
| `SHRT_MAX`       | Valor máximo do tipo `short int`            | 32767               |
| `USHRT_MAX`      | Valor máximo do tipo `unsigned short int`   | 65535               |
| `INT_MIN`        | Valor mínimo do tipo `int`                  | -2147483648         |
| `INT_MAX`        | Valor máximo do tipo `int`                  | 2147483647          |
| `UINT_MAX`       | Valor máximo do tipo `unsigned int`         | 4294967295          |
| `LONG_MIN`       | Valor mínimo do tipo `long int`             | Depende da plataforma (geralmente -2147483648 ou -9223372036854775808) |
| `LONG_MAX`       | Valor máximo do tipo `long int`             | Depende da plataforma (geralmente 2147483647 ou 9223372036854775807) |
| `ULONG_MAX`      | Valor máximo do tipo `unsigned long int`    | Depende da plataforma (geralmente 4294967295 ou 18446744073709551615) |

