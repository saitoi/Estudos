---
aliases:
  - metodos methods
tags:
  - java/✖
  - java/metodo
date: 2023-08-09
time: 15:53
complete:
---

# Métodos

> $\textit{Definição.}$ Unidade de código (semelhante à uma função) que executa uma ação específica, disposto em unidades modulares definidas em uma classe.

### $\textup{Principais características}$

1. **Sobrecarga de métodos**: Podemos definir métodos distintos com o mesmo nome, porém parâmetros distintos. Denominamos isso de [[Noções Básicas de POO#^4b82fd|polimorfismo de sobrecarga ou estático]] em linguagens orientadas a objetos.

2. **Visibilidade de métodos**: Podem ter diferentes níveis de visibilidade definidos pelos [[Java/Modificadores/Modificadores de Acesso|modificadores de acesso]].

3. **Tipos de métodos**: Métodos podem ser **estáticos** (==pertencem à classe==) ou de **instância** (==pertencem a objetos de uma classe==). Métodos estáticos são chamados usando o nome da classe, enquanto os de instância são chamados a partir do objeto.

> [!info] Métodos de Classe e Instância
> - **Métodos de Estáticos ou Classe**:
> Pertencem à classe como um todo e , portanto, podem ser acessados através do nome da classe pois não requerem a criação de um objeto para serem chamados. Um exemplo seria o método `Integer.MAX_VALUE`. Aqui está outro exemplo abaixo:
> ```java
> public class Operations {
> 	public static int sum(int a, int b)
> 		return a + b;
> 	
> 	public static int subtraction(int a, int b)
> 		return a - b;
> }
> 
> public class Main {
> 	public static void main (String[] args) {
> 		int ResultSum = Operations.sum(2, 8);                  /* Chamando método de classe */
> 		int ResultSubtraction = Operations.subtraction(10, 5); /* Chamando outro método de classe */
> 		
> 		System.out.println("Sum = " + ResultSum);
> 		System.out.println("Subtraction = " + ResultSubtraction);
> 	}
> }
> ```
> - **Métodos de Instância**:
> Pertencem a objetos específicos criados a partir de uma classe, sendo acessados a partir desse objeto e suas variáveis, tal como no exemplo abaixo:
> ```java
> public class Person {
> 	private String name;
> 	
> 	public Person(String name)
> 		this.name = name;
> 	
> 	public void greetings()
> 		System.out.println("Hello, my name is " + name);
> } 
> 
> public class Main {
> 	public static void main(String[] args) {
> 		Person person1 = new Person("Pedro");
> 		Person person2 = new Person("Rafaela");
> 		
> 		person1.greetings();  /* Chamando método de instância */
> 		person2.greetings();  /* Chamando outro método de instância */
> 	}
> }
> ``` 

## Estrutura de um método

A declaração de um método envolve a escolha de um nome (identificador), precedido do [[Java/Modificadores/Modificadores de Acesso|modificador de acesso]], do tipo do método (estático ou de instância) e do tipo de retorno deste método. Aqui está um exemplo abaixo:
```java
public static void MethodName(p1type p1, p2type p2, {..}) {
	/* Instruções no corpo do método */
	/* ... */
}
```

Após o identificador, detalhamos os parâmetros que serão passados para o método.

