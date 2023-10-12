---
alias: in_out_java scanner
tags: java/✖
date: 2023-08-14
time: 13:07
---

# Entrada e Saída

> $\textit{Definição.}$ Refere-se às operações de leitura e escrita de dados em um programa de computador.

A [[Python/Bibliotecas|biblioteca]] padrão do Java já fornece as classes e métodos necessários para realizar as operações de entrada e saída. Abordarei as principais operações subdividindo-as em suas respectivas classes:
1. **Entrada (E)**
- Para realizar a leitura de dados do teclado, usualmente, empregamos a classe padrão `Scanner` juntamente da variável estática `System.in`. Entretanto, apresentaremos brevemente outras técnicas para entrada de dados:

| Técnica                        | Descrição                                                                                                                                                 |
|:------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `System.in`                    | Assim como `System.out`, Java providencia o `System.in` que <br> permite a leitura de dados do console ou terminal.                                       |
| `System.console`               | Solicita ao usuário informação e realiza a leitura de uma linha <br> única. No entanto, não é compatível com IDEs, resultando em <br> erro de compilação. |
| Argumentos da Linha de Comando | Refere-se à chamada do programa em Java e especificação dos <br> seus dados na chamada. Todavia, não é possível criar aplicações <br> interativas.        |
| `Scanner`                      | Forma padrão para a leitura de dados que utiliza `System.in` <br> ou arquivos.                                                                            |

- **Classe Scanner**:
	- Para realizarmos a leitura de dados por meio dessa classe, criamos uma instância da classe `Scanner` com o parâmetro de entrada `System.in` e, por fim, empregamos algum dos métodos de `Scanner` para a obtenção dos dados. Aqui está um exemplo:

```java
	public class EntradaExemplo {
	    public static void main(String[] args) {
	        Scanner scanner = new Scanner(System.in);
	        
	        System.out.print("Digite um número inteiro: ");
	        int numero = scanner.nextInt();
	        
	        System.out.println("Você digitou: " + numero);
	        
	        scanner.close();
	    }
	}

```
 
- Os principais métodos da classe `Scanner` para o tratamento de dados será descrito abaixo:

| Método          | Descrição                                            | Exemplo                                       | 
| --------------- | ---------------------------------------------------- | --------------------------------------------- |
| `next()`        | Lê o próximo token como uma string                   | `String nome = scanner.next();`               |
| `nextLine()`    | Lê a próxima linha inteira como uma string           | `String linha = scanner.nextLine();`          |
| `nextInt()`     | Lê o próximo token como um inteiro                   | `int idade = scanner.nextInt();`              |
| `nextDouble()`  | Lê o próximo token como um número de ponto flutuante | `double altura = scanner.nextDouble();`       |
| `nextBoolean()` | Lê o próximo token como um valor booleano            | `boolean verdadeiro = scanner.nextBoolean();` |

- Vale lembrar que é preciso importar a biblioteca `java.util.Scanner` para a utilização das funcionalidades dessa classe.

2. **Saída (S)**
	- Para realizar a impressão dos dados no monitor ou terminal, usualmente, empregamos o objeto estático `System.out` atrelado ao método `.print` ou `.println`. Posto isso, apresentaremos as principais formas de saída:

| Técnica              | Descrição                                                                                                |
| -------------------- | -------------------------------------------------------------------------------------------------------- |
| Método `print`       | Exibe uma mensagem simples na tela, sem adição <br> do quebra-linha.                                     |
| Método `println`     | Semelhante ao `print`, no entanto adiciona o quebra-linha.                                               |
| Método `printf`             | Permite a formatação mais avançada da saída, <br> usando especificadores de formato semelhante à C       |
| Classe `PrintWriter` | Permite a criação de instâncias para o envio de <br> dados a arquivos externos ou fluxos personalizados. |
