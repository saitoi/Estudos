---
alias: overflow underflow
tags: java/✖
date: 2023-08-08
time: 11:41
---

# Transbordamento e Subfluxo

> $\textit{Definição.}$ Termos empregados para descrever situações em que um valor ultrapassa os limites do intervalo válido para um dado tipo de dados.

- Quando obtivermos um <ins>transbordamento ou overflow</ins>, o valor máximo irá contornar até o valor mínimo e continuará a processar sem erros.
- Quando obtivermos um <ins>subfluxo ou underflow</ins>, o valor mínimo irá contornar até o valor máximo e continuará a processar sem erros.

> [!note] Transbordamento e Compilação
> Aqui estão dois exemplos que irão compilar e resultarão em transbordamento em que um deles utiliza o conceito de [[Classes Empacotadoras|classes empacotadoras]].
> ```java
> int VaiCompilar = (Integer.MAX_VALUE + 1);
> int VaiCompilar = (2147483647 + 1);
> ```
> No entanto, a inicialização com um valor literal numérico superior a `Integer.MAX_VALUE` resultará em erro, pois o compilador avalia essa expressão na compilação. Aqui está um exemplo:
> ```java
> int NaoVaiCompilar = 2147483648;
> ```




