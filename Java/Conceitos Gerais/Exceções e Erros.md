---
aliases:
  - exception
  - excecao
  - errors_java
tags:
  - java
date: 2023-08-23
time: 21:33
---

# $\texttt{Exceções e Erros.}$

> $\textit{Definição de Exceções.}$ Eventos anormais que ocorrem durante a execução do programa e que podem interromper seu fluxo normal de execução.

A principal diferença entre **erros** e **exceções** é que erros representam condições graves e irrecuperáveis indicando problemas no ambiente de execução ou na máquina virtual Java, enquanto exceções são, normalmente, **eventos anormais e recuperáveis** que podem ser tratados para dar continuidade à execução do programa.

Podemos dividir as exceções em duas categorias, isto é, **exceções verificadas (checked exceptions)** e **exceções não verificadas (unchecked exceptions)**.

- **Exceções verificadas**: Exceções que o compilador exige o tratamento explícito e que ocorrem durante a compilação do programa. Exemplos incluem `IOException` e `FileNotFoundException`. Essas exceções herdam a classe `Exception`.
- **Exceções não verificadas**: Não exigem um tratamento explícito, sendo originadas durante a execução do programa. Em vista disso, essas exceções herdam a classe `RunTimeException`. Exemplos incluem `NullPointerException` e `IllegalArgumentException`.

Aqui está um diagrama das exceções em Java.

![[exceções.jpg]]

Como podemos ver, as exceções não verificadas derivam de `RunTimeException` que, por sua vez, é uma subclasse de `Exception`, enquanto o restante das exceções verificadas são subclasses de `Exception`.

Exemplo de erro: Estouro de memória.
$$
\begin{align}
&\begin{rcases}
\text{Unchecked exceptions} \\
\text{Runtime exception}
\end{rcases}\quad  \text{Exceções em tempo de execução.}&
\\ \\
&\begin{rcases}
\text{Checked exceptions}
\end{rcases}\quad \text{Java obriga o tratamento.}& 
\end{align}
$$

Aqui estão alguns exemplos das principais exceções e erros em Java:

| Exceção Verificada               | Descrição                                                                   |
| -------------------------------- | --------------------------------------------------------------------------- |
| `ArrayIndexOutOfBoundsException` | Lançada quando um índice de array está fora dos limites permitidos.         |
| `FileNotFoundException`          | Lançada ao tentar acessar um arquivo que não pode ser encontrado.           |
| `IOException`                    | Classe base para exceções de entrada/saída, indica problemas de I/O.        |
| `ClassNotFoundException`         | Lançada quando uma classe não pode ser encontrada durante a reflexão.       |
| `InterruptedException`           | Lançada quando uma thread é interrompida enquanto está em estado de espera. |
| `SecurityException`              | Lançada quando ocorre um problema de segurança.                             |
| **Exceções Não Verificadas**     |                                                                             |
| `RuntimeException`               | Exceção base para exceções não verificadas.                                 |
| `IllegalArgumentException`       | Lançada quando um argumento é inválido em um método.                        |
| `NumberFormatException`          | Lançada quando uma conversão de string para número falha.                   |
| `NullPointerException`           | Lançada quando uma referência a um objeto é nula e você tenta acessá-la.    |
| `ArithmeticException`            | Lançada quando ocorre um erro aritmético, como uma divisão por zero.        |
| **Erros**                        |                                                                             |
| `OutOfMemoryError`               | Lançada quando a JVM fica sem memória para alocar objetos.                  |
| `StackOverflowError`             | Lançada quando a pilha de chamadas de métodos fica muito grande.            |

## $\texttt{Tratamento de Exceções.}$

Para realizar o tratamento de exceções, empregamos os blocos de comando `try` e `catch`  ou simplesmente usamos o `throw` para lançar uma exceção desejada.

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

Erros são mais danosos que exceções. Podemos tratar as exceções, mas os erros não. Aqui está um outro exemplo de uma exceção:

```java
public class Principal {
	public static void main(String[] args) {
		metodo1();
	}
	public static void metodo1() {
		metodo2();
	}
	public static void metodo2() {
		ContaCorrente cc1 = new ContaCorrente(1);
		try {
			for (int i = 0; i <= 15; i++) {
				cc1.deposita(100+i);
				if (i == 5)
					cc1 = null;
			}
		} catch (NullPointerException e1) {
			System.out.print("Exceção: " + e1);
		}
	}
	public static void metodo3a() {
		try {
			new java.io.FileInputStream("Arquivo.txt");
		} catch (java.io.FileNotFoundException e1) {
			System.out.print("Não foi possível abrir o arquivo.");
		}
	}
	public static void metodo5() throws {
		new java.io.FileInputStream("Arquivo.txt");
		
	}
}
```

## <span style="color:#ff0000"> Aprender como usar </span>`throws`

Considere a classe separada `ContaCorrente`.

```java
public class ContaCorrente {
	private int num;
	private float saldo;
	
	public ContaCorrente(int num) {
		this.num = num;
	}
	public void deposita(float valor) {
		this.saldo += valor;
	}
}
```

