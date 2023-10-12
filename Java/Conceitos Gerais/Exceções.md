---
alias: exception
tags: java
date: 2023-08-23
time: 21:33
---

# Exceções

> $\textit{Definição.}$ Eventos anormais que ocorrem durante a execução do programa e que podem interromper seu fluxo normal de execução.

Aqui estão alguns exemplos de exceções em Java:

| Exceção                          | Descrição                                                                   |
| -------------------------------- | --------------------------------------------------------------------------- |
| `ArithmeticException`            | Lançada quando ocorre um erro aritmético, como uma divisão por zero.        |
| `NullPointerException`           | Lançada quando uma referência a um objeto é nula e você tenta acessá-la.    |
| `ArrayIndexOutOfBoundsException` | Lançada quando um índice de array está fora dos limites permitidos.         |
| `FileNotFoundException`          | Lançada ao tentar acessar um arquivo que não pode ser encontrado.           |
| `IOException`                    | Classe base para exceções de entrada/saída, indica problemas de I/O.        |
| `NumberFormatException`          | Lançada quando uma conversão de string para número falha.                   |
| `ClassNotFoundException`         | Lançada quando uma classe não pode ser encontrada durante a reflexão.       |
| `InterruptedException`           | Lançada quando uma thread é interrompida enquanto está em estado de espera. |
| `IllegalArgumentException`       | Lançada quando um argumento é inválido em um método.                        |
| `SecurityException`              | Lançada quando ocorre um problema de segurança.                             |
| `OutOfMemoryError`               | Lançada quando a JVM fica sem memória para alocar objetos.                  |
| `StackOverflowError`             | Lançada quando a pilha de chamadas de métodos fica muito grande.            |

Para lidar com exceções, empregamos os blocos de comando `try`, `catch` e `finally`. Aqui está uma explicação detalhada de cada um deles:

1. `try`: O bloco de comando `try` engloba o trecho de código que pode lançar exceções, permitindo esses casos de forma mais controlada.
2. `catch`: O bloco de comando `catch` realiza a captura da exceção, isto é, recebendo-a como parâmetro. Posto isso, o restante do bloco é executado, alertando ao usuário acerca da exceção ou tratando-a.
3. `finally`: O bloco de comando `finally` é executado independentemente da presença ou não da exceção, sendo o último nesse contexto.

Exemplo de tratamento de exceção com os comandos mencionados:

```java
public class ExemploExcecao {
    public static void main(String[] args) {
        int numerador = 10;
        int denominador = 0;
        
        try {
            int resultado = numerador / denominador;
            System.out.println("Resultado: " + resultado);
        } catch (ArithmeticException e) {
            System.out.println("Erro de divisão por zero: " + e.getMessage());
        } finally {
            System.out.println("Bloco finally executado.");
        }
        
        System.out.println("Fim do programa.");
    }
}
```
