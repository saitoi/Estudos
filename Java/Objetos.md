---
aliases:
  - instancia
  - object
  - objeto
tags:
  - java
date: 2023-08-19
time: 15:09
complete:
---

# Objetos

> $\textit{Definição.}$ Instância de uma classe, ou seja, entidade concreta que engloba os atributos e métodos da classe. **Objeto** $\equiv$ **Instância**. 

## $\texttt{Declaração.}$

A criação de uma instância é realizada por meio do comando `new` juntamente da chamada do [[Método Construtor|método construtor]] para a classe que desejamos instanciar. Aqui está um exemplo.

```c
public class Person {
	private String nome;
	private int idade;
	
	public Person(String nome, int idade) {
		this.nome = nome;
		this.idade = idade;
	}
	/* ... */
}

/* Na função "Main" */
Person pessoa1 = new Person("Pedro", 18);
Person pessoa2 = new Person("Rafaela", 4);
```

- [i] Vale notar que não é necessário empregar o comando `new` para as [[Classes Empacotadoras|classes empacotadoras]], pois a conversão é feita automaticamente.

Considere o exemplo da instância de uma `String` ou um valor decimal `Double`.

```java
String fruta = "Abacate";
String fruta = new String("Maçã");  /* Também é válido */
Double pi = 3.14;
Double pi = new Double(3);
```







