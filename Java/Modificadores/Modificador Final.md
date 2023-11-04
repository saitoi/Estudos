---
alias: final
tags: java/aula_3
date: 2023-08-22
time: 21:50
---

# Modificador Final

> $\textit{Definição.}$ Modificador reservado para indicar que algo(, isto é, variáveis, métodos ou classes) não pode ser alterado.

O modificador `final` pode ser implementado em alguns contextos, aqui estão eles:

1. **Variáveis finais:**
	- Constante que não pode ser alterada após a atribuição inicial. Ela deve ser inicializada no momento da declaração ou no construtor da classe, aqui está um exemplo:
	```java
	public class ExemploVariavelFinal {
    final int CONSTANTE = 10;

    public static void main(String[] args) {
        ExemploVariavelFinal exemplo = new ExemploVariavelFinal();
        // exemplo.CONSTANTE = 20; // Isso geraria um erro de compilação
        System.out.println(exemplo.CONSTANTE);
	    }
	}
	```

2. **Métodos finais:**
	- Método final em uma classe não pode ser sobrescrito por subclasses. Útil quando se deseja garantir que um método seja alterado por subclasses, aqui está um exemplo:
	```java
	public class ClasseBase {
	    final void metodoFinal() {
        System.out.println("Este é um método final.");
	    }
	}
	
	public class Subclasse extends ClasseBase {
    // Não é possível sobrescrever o métodoFinal aqui
	}
	```

3. **Classes finais:**
	- Uma classe final não pode ser estendida por outras classes. Útil quando se deseja garantir que uma classe não seja subclasseada, aqui está um exemplo:
	```java
	public final class ClasseFinal {
    // Conteúdo da classe
	}
	
	// A seguinte linha geraria um erro, pois não é possível estender uma classe final
	public class Subclasse extends ClasseFinal { ... }
	```

