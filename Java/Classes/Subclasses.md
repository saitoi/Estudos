---
aliases:
  - sub
  - extends
  - implement
tags:
  - java/✖
date: 2023-08-15
time: 11:26
complete:
---

# Subclasses

> $\textit{Definição.}$ Classe que herda atributos e comportamentos (métodos) de uma classe originária ([[Superclasse|superclasse]]), podendo adicionar novos membros alterar os existentes.

## $\texttt{Comando extends.}$

Identificador necessário na declaração de uma subclasse que herda as características da superclasse. Aqui está um exemplo da classe `Pessoa` com sua subclasse `Estudante` as quais precisariam ser definidas em arquivos distintos.

```java
public class Pessoa {
	private String nome; 
	private int idade; 
	
	public Pessoa(String nome, int idade) {
		this.nome = nome;
		this.idade = idade;
	}
}

public class Estudante extends Pessoa {
	private int matricula;
	
	public Estudante(String nome, int idade, int matricula) {
		super(nome, idade);
		this.matricula = matricula;
	}
}
```

A subclasse final do programa pode ser indicada pelo modificador `final`, a explicação mais apurada está descrita em [[Modificador Final]].

## $\texttt{Comando implements.}$

