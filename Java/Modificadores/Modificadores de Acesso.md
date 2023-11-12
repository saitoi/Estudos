---
aliases:
  - access_modifiers_java
tags:
  - java
date: 2023-08-09
time: 14:58
complete: true
---

# Modificadores de Acesso

> $\textit{Definição.}$ Palavras-chaves que definem a visibilidade de classes, métodos, campos e construtores no programa.

Os principais modificadores em Java incluem `public`, `protected`, `default` e `private`, de modo que a utilização de cada um varia se estivermos tratando de **classes** ou **membros**. Abordarei cada um dos casos mencionados abaixo:

## $\texttt{Modificadores de Classes.}$

Os modificadores disponíveis para as classes estão descritos abaixo:

- `public`: Classe acessível por qualquer classe em qualquer pacote
- `default`: Sem modificador algum, classe restrita ao pacote em que foi criada.
- `static`: Disponível para [[Classe Interna|classes internas]], isolando-as das classes externas.

### $\texttt{Modificador Static para Classes Internas.}$

A utilização do modificador `static` para classes internas permite modificá-las com relação às classes internas padrões. Aqui estão algumas das principais diferenças:

- **Acesso direto**: Não requer a criação de um objeto da classe interna para ser acessada, tal como um método estático. Considere as classes `Externa` e `Interna` em que a segunda está aninhada na primeira:

```java
public class Principal {
	public static void main(String[] args) {
		Externa.Interna classeInterna = new Externa.Interna();
		classeInterna.algumMetodoInterno();
		/* ... */
	}
}
```

- **Escopo limitado**: Não possui acesso direto a membros da classe externa, pois é independente e não pode acessar instâncias da classe externa.

## $\texttt{Modificadores de Membros.}$

Os modificadores disponíveis para os membros de uma classe qualquer são:

- `public`: Membro acessível por qualquer classe/pacote, não possui restrições de visibilidade.
- `protected`: Membro acessível por todas as classes do mesmo pacote, bem como suas subclasses (heranças).
- `default`: Acessível por todas as classes do mesmo pacote.
- `private`: Acessível somente no interior da mesma classe, subclasses não possuem acesso.

- [i] A modificação ou acesso a campos privados pode ser realizada por meio de [[Getters e Setters]].
