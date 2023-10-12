---
aliases:
  - switch yield
tags:
  - java
date: 2023-08-14
time: 11:58
complete: true
---

# Instrução Switch Aprimorada

## $\texttt{Sintaxe nova}$

```java
switch (switchValue) {
	case 1 -> System.out.println("Value is 1.");
	case 2 -> System.out.println("Value is 2.");
	case 3, 4, 5 -> {
		System.out.println("Value is 3, 4 or 5.");
		System.out.println("Actually value is " + switchValue);
	}
	default -> System.out.println("Isn't 1, 2, 3, 4 or 5.");
}
```

## $\texttt{Sintaxe antiga}$

```java
switch (switchValue) {
	case 1:
		System.out.println("Value is 1");
		break;
	case 2:
		System.out.println("Value is 2.");
		break;
	case 3:
	case 4:
	case 5:
		System.out.println("Value is 3, 4 or 5.");
		System.out.println("Actually value is " + switchValue);
		break;
	default:
		System.out.println("Isn't 1, 2, 3, 4 or 5.");
}
```

## $\texttt{Comando yield}$

Palavra reservada empregada para retornar um valor da expressão do `switch` mais recente, ao contrário da abordagem tradicional com `break`. Aqui está um exemplo:

```java
return switch (dayOfWeek) {
	case 1, 2, 3, 4, 5 -> "Weekday";
	case 6, 7 -> "Weekend";
	default -> {
		yield "Invalid day";
	}
};
```

> [!info] Tipos Válidos para Switch
>
> |||||
> |:-:|:-:|:-:|:-:|:-:|:-:|
> |`byte`|`short`|`int`|`char`|`enum`|
> |`Byte`|`Short`|`Integer`|`Character`|`String`|

