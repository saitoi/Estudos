---
aliases:
  - construtor
  - constructor
  - this
tags:
  - java/metodo
date: 2023-08-13
time: 13:14
complete:
---

# Método construtor

> $\textit{Definição.}$ Tipo especial de [[Métodos|método]] usado para inicializar os objetos de uma classe, sendo executado automaticamente na criação de um novo objeto dessa classe.

### $\textup{Principais características.}$

1. **Principal função** é definir atributos e características na criação de instâncias e, por isso, não é obrigatório.
2. Nome do método construtor deve ser o mesmo da classe.
3. Não possui um tipo de retorno, nem mesmo `void`.
4. Construtor pode ter parâmetros, permitindo a passagem de valores na criação do objeto.
5. Java fornecerá um construtor automaticamente, caso você não defina um explicitamente.

Aqui está um exemplo de um método construtor para a classe `Pessoa`:

```java
public class Pessoa {
	private String nome;
	private int idade;
	
	public Pessoa(String nome, int idade) {
		this.nome = nome;
		this.idade = idade;
	}
	
	/* Outros métodos da classe .. */
}
```

**Obs.** Podemos inicializar outras variáveis dentro do método construtor sem que sejam passadas como parâmetro, tal como no exemplo da classe `RobotXY`:

```java
public class RobotXY {
	String nome = "Pedro Saito"
	long DRE = 122149392;
	
	private linhaCentro;
	private colunaCentro;  /* Outras variáveis .. */
	
	public class RobotXY(String nome, long DRE) {
		this.nome = nome;
		this.DRE = DRE;
		linhaCentro = colunaCentro = -1;  /* Outras variáveis .. */
		/* ... */
	}
	
	/* Resto do código da classe .. */
	
}
```

As variáveis `linhaCentro`, `colunaCentro`, dentre outras foram inicializadas no interior do construtor embora não tenham sido passadas como parâmetros. Assim sendo, ao criar instâncias novas da classe `RobotXY` esses objetos terão essas variáveis inicializadas por padrão para o mesmo valor, que seria $-1$ no exemplo dado.

## $\texttt{Comando this.}$

Palavra-chave em Java usada para se referir à instância atual de uma classe. Empregada dentro dos métodos da classe para evitar ambiguidade na escolha dos atributos referentes à instância específica.

```java
public class Exemplo {
	public String nome = "Pedro";
	
	public Exemplo(String nome) {
		this.nome = nome;
	}
}
```

O objeto da classe `Exemplo` terá seu atributo `nome` inicializado com o parâmetro na chamada do construtor ao invés de receber a string `"Pedro"` declarada no interior da classe.