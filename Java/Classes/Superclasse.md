---
aliases:
  - super
tags:
  - java/Classes
date: 2023-09-03
time: 22:56
complete:
---

# Superclasses

> $\textit{Definição.}$ Classe originária da qual outras classes ([[Subclasses|subclasses]]) herdam atributos e métodos.

## $\texttt{Comando super}$

Referência para a chamada de construtores da classe pai (superclasse) e inicialização das partes dessa classe, sendo comumente utilizada com [[Noções Básicas de POO#^a09fda|herança]]. Suponha a existência da classe `Veiculo` e sua subclasse `Automovel`, aqui está um exemplo abaixo:

```java
public class Veiculo {
	
	public Veiculo(String chassi) {
		this.chassi = chassi;
	}
	/* ... */
}

public class Automovel extends Veiculo {
	String tipo;
	
	public Automovel(String chassi, String tipo) {
		super(chassi);
		this.tipo = tipo;
	}
	/* ... */
}
```

- [i] O comando `super` deve ser o primeiro na chamada dos construtores das subclasses.

## $\texttt{Modificador abstract.}$

Palavra-chave para declarar classes ou métodos que não podem ser instanciados diretamente, mas fornecem um protótipo para implementação de subclasses.

Aqui está um exemplo da superclasse abstrata `Animal` juntamente das subclasses.

```java
public abstract class Animal {
	
}
```

## $\texttt{Modificador interface.}$



## $\texttt{Class Object}$

Superclasse base de todas as outras classes padrões do Java.

**Principais métodos:**

|Método|Descrição|
|---|---|
|`equals(Object obj)`|Compara o conteúdo apontado por um objeto com outro.|
|`toString()`|Por padrão, retorna o nome da classe junto do hash do objeto.|
|`hashCode()`|Retorna um código hash do objeto.|
|`getClass()`|Retorna a classe do objeto como um objeto `Class`.|
|`clone()`|Cria uma cópia superficial (shallow copy) do objeto.|
|`finalize()`|Chamado pelo coletor de lixo antes de liberar a memória ocupada pelo objeto.|
|`wait()`, `notify()`, `notifyAll()`|Usados para controle de concorrência e sincronização entre threads.|

**Obs.** O comando `.equals(Object obj)` realiza a comparação do conteúdo das variáveis e não de seus endereços como é feito por meio do comando `==`.

Exemplo da utilização do método `toString()` abaixo:

```java
public class Carro {
	private String marca;
	private String modelo;
	private int ano;
	
	public Carro(String marca, String modelo, int ano) {
		this.marca = marca;
		this.modelo = modelo;
		this.ano = ano;
	}
	
	public static void main(String[] args) {
		Carro carro = new Carro("Toyota", "Corolla", 2022);
		System.out.println(carro.toString());    /* Saída: Carro@36baf30c */
	}	
}
```

Aqui está um exemplo da utilização do método `.equals(Obj object)` na classe `Pessoa` e seus atributos.

```java
public class Pessoa {
    private String nome;
    private int idade;

    public Pessoa(String nome, int idade) {s
        this.nome = nome;
        this.idade = idade;
    }

    public static void main(String[] args) {
        Pessoa pessoa1 = new Pessoa("Alice", 25);
        Pessoa pessoa2 = new Pessoa("Bob", 30);
        Pessoa pessoa3 = new Pessoa("Alice", 25);

        System.out.println("pessoa1 equals pessoa2: " + pessoa1.equals(pessoa2));  /* pessoa1 equals pessoa2: false */
        System.out.println("pessoa1 equals pessoa3: " + pessoa1.equals(pessoa3));  /* pessoa1 equals pessoa2: true */
    }
}
```
