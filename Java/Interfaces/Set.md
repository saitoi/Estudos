---
aliases:
  - set_interface
  - hashset
  - set
tags:
  - java
date: 2023-11-12
time: 13:09
complete:
---

# Set

> $\textit{Definição.}$ Interface pertencente ao Framework de Coleções, sendo sua principal característica não permitir elementos duplicados. Modela o comportamento matemático de um conjunto em que cada elemento é único.

Vale notar que não há garantias de ordenação dos elementos na interface `Set`, apenas em algumas classes que implementam essa interface, tal como a classe `LinkedHashSet`.

Dentre as principais classes que implementam a interface `Set`, podemos citar:

1. `HashSet`: Implementação da interface baseada na tabela de dispersão ou código hash dos objetos. Essa aplicação permite elementos nulos (`null`), bem como não mantém a ordem específica dos objetos na coleção.
3. `LinkedHashSet`: Mantém a ordem de inserção dos elementos conforme a tabela de dispersão de modo que cada entrada da tabela mantém uma referência para a próxima e para a anterior, formando uma lista duplamente encadeada.
4. `TreeSet`: Implementação baseada em árvore balanceada que mantém a ordem dos elementos seguindo a ordem natural de inserção ou por meio de um comparador fornecido no momento de criação. Essa aplicação não permite termos nulos (`null`).

## $\texttt{Classe HashSet.}$

> $\textit{Definição.}$ Classe da biblioteca de Java que pertence à interface `Set`. Essa interface é útil para o armazenamento de um conjunto de elementos únicos, sem permitir duplicatas. 

De antemão, precisamos descrever as principais características da interface `Set`.

1. A interface `Set` faz parte do framework de coleções de Java, sendo uma interface de `Collection`.
2. Os conjuntos não permitem elementos duplicados, mais precisamente que possuam os mesmos endereços.
3. Não há garantia de ordem de elementos em um conjunto, embora existam subclasses que implementem essa funcionalidade tal como a `LinkedHashSet`.
4. Trataremos da implementação `HashSet`, no entanto as principais incluem `HashSet`, `LinkedHashSet` e `TreeSet`.

### $\texttt{Hashcode.}$

O `HashSet` em Java depende do **código hash** dos objetos para seu funcionamento. Em resumo, o código hash é um valor calculado a partir do conteúdo dos objetos, sendo fundamental para otimizar a busca e organização de dados em estruturas como tabelas hash.

Em Java, o código hash é gerado usando o método `hashCode` da classe `HashSet`. No entanto, é possível personalizar essa implementação ao sobrescrever o método. A implementação padrão na classe `Object` usa o endereço de memória para distinguir objetos, mas isso pode não ser adequado para todos os programas.

Aqui está um exemplo de um dos empecilhos na utilização do `hashCode()` padrão.

```java
public class Pessoa {
	private String nome;
	private int idade;
	/* Método construtor.. */
	/* ... */
}

/* Na função "Main" */
HashSet<Pessoa> listaPessoas = new HashSet<>();
Pessoa p1 = new Pessoa("Pedro", 19);
Pessoa p2 = new Pessoa("Pedro", 19);

listaPessoas.print();
/*  Pedro 19
	Pedro 19
	..
*/
```

Como podemos notar, embora as variáveis `p1` e `p2` possuam endereços distintos na memória, os campos identificadores `nome` e `idade` possuem os mesmos valores em ambas as variáveis. Isso implica que o código hash é diferente o que não está certo do ponto de vista de implementação da classe `Pessoa`.

Por isso, é realizada a [[Noções Básicas de POO|sobrescrita]] desse método para adaptá-lo ao programa/à classe em questão. Aqui está um exemplo da necessidade de rescrever o método `hashCode` a fim de se adaptar ao programa em questão.

```java
public class Conta {
	private int codigo;
	/* ... */
}

@Override
public int hashCode() {
	return this.codigo;
}

@Override
public boolean equals(Object obj) {
	if (obj == this) {
		return true;
	}
	if (obj instanceof Objeto) {
		if  (obj.hashCode == this.hashCode) {
			return true;
		}
	}
	return false;
}
```

- [i] Ao rescrever o método `hashCode()`, precisamos também rescrever o método `equals` pois, usualmente, a função para adicionar novos elementos à coleção, isto é, `.add`, emprega os dois métodos para realizar a comparação.







