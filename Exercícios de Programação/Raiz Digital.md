---
aliases:
  - digital_root
tags:
  - java
date: 2023-09-03
time: 12:19
complete: true
---

# $\text{Raiz Digital}$

> [!info] Enunciado
> A **raiz digital** é a soma recursiva de todos os dígitos em um número.
> 
> Dado $n$, some os dígitos de $n$. Se esse valor tiver mais de um dígito, continue reduzindo dessa maneira até que seja produzido um número de um único dígito. A entrada será um número inteiro não negativo.    
> **Exemplos:**$$
> \begin{flalign*}
> &16 \rightarrow 1 + 6 = 7&& \\ \\
> &942 \rightarrow 9 + 4 + 2 = 15 \rightarrow 1 + 5 = 6&& \\ \\
> &132189 \rightarrow 1 + 3 + 2 + 1 + 8 + 9 = 24 \rightarrow 2 + 4 = 6&& \\ \\
> &493193 \rightarrow 4 + 9 + 3 + 1 + 9 + 3 = 29 \rightarrow 2 + 9 = 11 \rightarrow 1 + 1 = 2&&
> \end{flalign*}
> $$

## $\texttt{Minha solução.}$

Para encontrar a raiz digital, implementei um algoritmo recursivo que verifica se o inteiro $n$ possui um único dígito e, caso contrário, realiza a soma dos dígitos de $n$ recursivamente até que a condição seja atendida. 

```java
public class DGRoot {
	public static int digital_root(int n) {
		if (n < 10) {
			return n;
		}
		String number = String.valueOf(n);
		int sum = 0;
		for (char digit : number.toCharArray()) {
			sum += (int) digit - '0';
		}
		return digital_root(sum);
	}
}
```

## $\texttt{Solução ideal.}$

A solução ideal de uma linha está descrita abaixo:

```java
public class DGRoot {
	public static int digital_root(int n) {
		return (n != 0 && n % 9 == 0) ? 9 : n % 9;
	}
}
```

**Explicação.** A resolução acima envolve uma característica da divisibilidade por $9$, isto é, se a soma dos dígitos de um número (inteiro) for divisível por $9$, então o número é um múltiplo de $9$.

**Demonstração.** A soma dos algarismos de $n$ é divisível por $9$ se, e somente se, $n$ é um múltiplo de $9$.
Traduzindo em termos matemáticos, considere $n$ contendo os seguintes algarismos:

$$
n=a_k\,a_{k-1}\;..\;a_2\,a_1\,a_0
$$

Se a soma dos algarismos de $a_0$ até $a_k$ for divisível por $9$, então $n$ é um múltiplo de $9$ também, tal como abaixo:

$$
\exists\;p\in\Bbb{N},\Big(\sum_{i=0}^{k}a_i=9p\iff\exists\;m\in\Bbb{N},(n=9m)\Big)
$$

Dada a proposição acima, demonstraremos a ida em um primeiro momento, isto é, **se a soma dos algarismos de $n$ for divisível por $9$, então $n$ é um múltiplo de $9$.** Portanto, iniciaremos a prova propondo algumas definições. Podemos representar $n$ da seguinte forma:

$$
\begin{align*}
&n=a_k\cdot10^k+a_{k-1}\cdot10^{k-1}+\,...\,+a_2\cdot10^{2}+a_1\cdot10+a_0 \\ \\
&n=\big[a_k\cdot(10^k-1)+\,...+\,a_2\cdot(99)+a_1\cdot9\big]-(a_k+\,...\,+a_2+a_1+a_0)
\end{align*}
$$

Como podemos observar, a primeira parte da equação à direita é divisível por $9$, pois cada fator $a_0,a_1,a_2,\,...\,a_{k-1},a_k$ é multiplicada por um fator $10^i-1,(\,\forall\;i\in[\,0,k\,]\,)$. Assim sendo, essa primeira parte será denotada $9l$, isto é, existe um $l$ que multiplicado por $9$ resultará na expressão mencionada.

$$
\begin{align*}
&\exists\;l\in\Bbb{N},\Big( n=\underbrace{\big[a_k\cdot(10^k-1)+\,...+\,a_2\cdot(99)+a_1\cdot9\big]}_{9l}-(a_k+\,...\,+a_2+a_1+a_0)\Big) \\ \\
\,&n=9l-(a_k+\,...\,+a_2+a_1+a_0)
\end{align*}
$$

Como partimos da suposição que $\sum_{i=0}^{k}a_i=9p$, faremos a devida substituição na expressão acima.

$$
\begin{align*}
&n=9l-9p \\ \\
&\boxed{n=9\,(l-p)}\quad\blacksquare
\end{align*}
$$

Por fim, deduzimos que $n$ é um múltiplo de $n$, concluindo a prova da ida.    
Outrossim, nos resta demonstrar a volta, ou seja, **se $n$ é múltiplo de $9$, então a soma dos algarismos de $n$ será divisível por $9$.** Utilizaremos um raciocínio semelhante para provar a volta, começaremos da mesma forma. Como supomos que $n$ é múltiplo de $9$,

$$
\begin{align*}
&\exists\;m\in\Bbb{N},\Big(n=a_k\cdot10^k+a_{k-1}\cdot10^{k-1}+\,...\,+a_2\cdot10^{2}+a_1\cdot10+a_0=9m\Big)\\ \\
&\big[a_k\cdot(10^k-1)+\,...+\,a_2\cdot(99)+a_1\cdot9\big]-(a_k+\,...\,+a_2+a_1+a_0)=9m \\ \\
\end{align*}
$$
Como vimos anteriormente, a primeira parte da equação à esquerda é divisível por $9$. Desse modo, substituiremos pelo mesmo fator que a expressão anterior.

$$
\begin{align*}
\underbrace{\big[a_k\cdot(10^k-1)+\,...+\,a_2\cdot(99)+a_1\cdot9\big]}_{9l}-(a_k+\,...\,+&a_2+a_1+a_0)=9m \\ \\
9l-(a_k+\,...\,+a_2+a_1+a_0)=&\,9m \\ \\
\boxed{9\,(l-m)=\sum_{i=0}^{k}a_i}\quad\blacksquare
\end{align*}
$$

Por fim, concluímos que o somatório dos algarismos de $n$ é um múltiplo de $9$ como previsto. Posto isso, podemos analisar cada caso do operador ternário.

1. `return 9`: O método para encontrar a raiz digital deve retornar $9$ caso $n$ for divisível por $9$ e for diferente de zero, pois teríamos o seguinte caso. Aqui está uma ilustração do processo:

$$
\begin{align*}
(n\,\small{\%}\,9&)==0 \\
&\Downarrow \\
(\sum_{i=0}^{k}a_1\,&\small{\%}\,9)==0 \\
&\Downarrow \\
(\sum_{i=0}^{k}a_1\,&\small{\%}\,9)==0 \\
&\Downarrow \\ &\;\,\vdots \\ &\Downarrow \\
(\small 9\small{\%}9&)==0 \\
&\Downarrow \\
&\;9
\end{align*}
$$
Como concordamos que a soma dos algarismos de $n$ é divisível por $9$ e, dado que o processo se repete para cada soma consecutiva, podemos concluir que o último termo terá de ser divisível por $9$. Assim sendo, o menor termo divisível por $9$ é o próprio $9$.

2. `return n % 9`: 