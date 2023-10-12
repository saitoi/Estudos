---
alias: null
tags: ⓒ
date: 2023-08-26
time: 17:55
---

# Switch Case Intervalo

Uma aplicação do comando condicional `switch` consiste em especificar intervalos de valores para a variável que está sendo analisada.
**Ex.** Suponha que desejamos retornar os caracteres `'A'`, `'B'`, `'C'`, `'D'` e `'F'` de acordo a nota obtida pelo aluno em uma avaliação. Considere que o intervalo de valores está ligado às suas respectivas notas seguindo a tabela abaixo:

|           Intervalo           | Nota |
|:-----------------------------:|:----:|
| $90\leq\textit{score}\leq100$ |  A   |
| $80\leq\textit{score}\leq90$  |  B   |
| $70\leq\textit{score}\leq80$  |  C   |
| $60\leq\textit{score}\leq70$  |  D   |
|    $\textit{score}\leq60$     |  F   |

Implementando um `switch` com intervalo de valores, teríamos:

```c
char get_grade(int a, int b, int c) {
switch ((a + b + c) / 3){
	case 90 ... 100:
	return 'A'; 
  case 80 ... 89: 
    return 'B'; 
  case 70 ... 79: 
    return 'C'; 
  case 60 ... 69:
    return 'D'; 
  case 0 ... 59: 
    return 'F'; 
  default: 
    return '\0';
  }
}
```
