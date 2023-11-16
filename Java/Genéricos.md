---
aliases:
  - generic
tags:
  - java/Classes
date: 2023-10-10
time: 10:11
complete:
---

# $\texttt{Genéricos.}$

> $\textit{Definição.}$ Recurso que permite criar classes, interfaces, métodos e outras estruturas de dados que são parametrizadas por tipos de dados. Isso permite a criação de códigos flexíveis o suficiente para trabalharmos com diferentes tipos de dados.

Podemos definir uma variedade de recursos como foi dito. Esses recursos (classes, métodos e variáveis) serão especificadas nas seções abaixo.

## $\texttt{Classes Genéricas.}$

> $\textit{Definição.}$ Também conhecidas como **classes parametrizadas**, trata-se de um recurso que permite criar classes que podem operar com tipos de dados diferentes, ou seja, uma classe ou método pode ser reutilizado com vários tipos.

### $\texttt{Declaração.}$

A declaração de uma classe genérica em Java envolve a utilização do operador `<>` englobando um tipo genérico, normalmente representado com a letra maiúscula `T` e **sucedendo o identificador da classe**. Aqui está um exemplo:

```java
public class Team<T> {
	private T teamName;
	private T captainName
	private List<T> teamMembers = new ArrayList<>();
	
	public Team(T name, T captain) {
		this.teamName = name;
		this.captainName = captain;
	}
	public void addTeamMember(T newMember) {
		teamMembers.add(newMember);
	}
	public void getTeamName() {
		return this.teamName;
	}
	public void getTeamMembers() {
		for (T member : teamMembers) {
			System.out.println(member);
		}
	}
}

public static void main(String[] args) {
    Team<String> footballTeam = new Team<>("Dream Team", "John");
    
    footballTeam.addTeamMember("Player1");
    footballTeam.addTeamMember("Player2");
    footballTeam.addTeamMember("Player3");
	
    System.out.println("Team Name: " + footballTeam.getTeamName());
    System.out.println("Captain: " + footballTeam.getCaptainName());
    System.out.println("Team Members: \n" + footballTeam.getTeamMembers());
    }
}
```

Dentre as particularidades de uma classe genérica, temos que a declaração de uma instância da classe genérica é realizada por meio da especificação do tipo desejado para aquela classe, ou seja, no caso dado foi `Team<String> footballTeam`. Por fim, o construtor da classe genérica deve incluir os caracteres `<>`, tal como `new Team<>("Dream Team", "John")`.

### $\texttt{Uso Bruto de uma Classe Genérica.}$

Ao utilizar classes genéricas, podemos fazer referência à classe ou criar instâncias desta. No entanto, é possível implementar classes genéricas sem especificar nenhum parâmetro, denominamos isso de **uso bruto de uma classe genérica**.

Considere o exemplo da classe genérica `GenericClass<T>` e teremos:

```java
public class GenericClass<T> {
    private T value;

    public GenericClass(T value) {
        this.value = value;
    }

    public T getValue() {
        return value;
    }

    public void setValue(T value) {
        this.value = value;
    }
}

public class RawUseExample {
    public static void main(String[] args) {
        GenericClass<Integer> genericInteger = new GenericClass<>(42);
        GenericClass rawGeneric = genericInteger; // Uso de "raw" sem especificar o tipo
        
        Integer value = (Integer) rawGeneric.getValue(); // É necessário fazer cast para Integer
        System.out.println(value);
    }
}
```

Como podemos ver, temos um "raw use" da classe `GenericClass` ao atribuir à variável `value` e usando o casting `(Integer)`.

## $\texttt{Métodos Genéricos.}$

Os métodos definidos com a **palavra-chave `<T>`** são ditos métodos genéricos os quais podem estar contidos ou não em uma classe genérica. Vale notar que nos métodos genéricos o fator `<T>` deve anteceder o tipo de retorno do método. Aqui está um exemplo abaixo.

```java
public static <T> void imprimirLista(List<T> lista) {
	for (T objeto : lista) {
		System.out.println(objeto);
	}
}
```


