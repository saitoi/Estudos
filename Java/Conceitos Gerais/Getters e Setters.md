---
aliases:
  - getter
  - setter
tags:
  - java/aula_3
date: 2023-08-22
time: 10:22
---

# Getters e Setters

> $\textit{Definição.}$ Métodos usados para acessar e modificar os valores de campos privados de uma classe em Java. Refere-se ao conceito de [[Noções Básicas de POO#^c6cdc7|encapsulamento]].

- $\texttt{Getter (acessador)}$: Usado para obter o valor de um campo privado de uma classe.
- $\texttt{Setter (mutador)}$: Usado para modificar o valor de um campo privado de uma classe.

Aqui está um exemplo que engloba ambos os métodos:

```java
public class Classe1 {
	public int atrib1;
	public int atrib2;
	private int atrib3;
	
	public int getAtrib3() {       /* getter */
		return this.atrib3;
	}
	
	public void setAtrib3(int n) { /* setter */
		this.atrib3 = n;
	}
}

public class {
	public class void main(String[] args) {
		Classe1 c1 = new Classe1();
		System.out.print(c1.atrib2);   /* Erro de compilação */
		
		c1.atrib3 = 20;                /* Erro de compilação */
		c1.atrib1 = 18; 
		c1.setAtrib3(25);              /* Método "setAtrib3" */
	}
}
```

### $\textup{Principais vantagens.}$

1. **Encapsulamento.** Controle do acesso e modificação de atributos privados, útil para manter a integridade dos dados.
2. **Controle.** Os métodos **getter** e **setter** permitem realizar a validação e processamento personalizados no interior desses métodos.
3. **Flexibilidade.** Possibilidade de modificar a implementação interna do atributo sem necessidade de alterar significativamente o código.
