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

Os principais modificadores em Java incluem `public`, `protected`, `default` e `private`, de modo que a utilização de cada um varia se estivermos tratando de classes ou membros, isto é, métodos campos ou construtores. Abordarei cada um dos casos mencionados abaixo:

|             | **Classes**                                                                                                                                           |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `public`    | Classe acessível por qualquer outra classe em qualquer pacote.                                                                                        |
| `default`   | Classe acessível apenas por classes do mesmo pacote.                                                                                                  |
|  `static`           |   Disponível apenas para **classes internas**, isolando-as em relação à classe externa.                                                                                                                                                    |
|             | **Membros**                                                                                                                                           |
| `public`    | Membro acessível por qualquer classe ou pacote, não possui restrições de visibilidade.                                                                |
| `protected` | Membro acessível por todas as classes do mesmo pacote, bem como suas subclasses ([[Noções Básicas de POO#^a09fda\|herança]]).                         |
| `default`   | Membro acessível por todas as classes do mesmo pacote.                                                                                                |
| `private`   | Membro acessível somente pela mesma classe, subclasses não possuem acesso. A modificação de campos privados pode ser feita com [[Getters e Setters]]. |

## $\texttt{Static para classes internas}$

Principais características de classes internas e estáticas.

1. **Acesso direto.** Acessível diretamente, isto é, não requer a criação de um objeto da classe externa para ser acessada, **apenas da classe interna**.

- **Exemplo:** Suponha a classe externa `ClasseExterna` e a interna `ClasseInterna` e, por fim, o método da classe interna `.imprimirValor()`.

```java
public static void main(String[] args) {
	ClasseExterna.ClasseInterna interna = new ClasseExterna.ClasseInterna();
	interna.imprimirValor();      /* Acessado diretamente */
}
```

2. **Escopo.** Não possui acesso direto a membros da classe externa. É essencialmente independente e não pode acessar instâncias criadas da classe externa.

3. **Notação.** Como foi visto no exemplo acima, para criar objetos da classe interna empregamos a notação: `ClasseExterna.ClasseInterna obj = new ClasseExterna.ClasseInterna();`.
