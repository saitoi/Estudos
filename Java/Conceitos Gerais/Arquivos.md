---
aliases: 
tags:
  - java
date: 2023-11-21
time: 10:11
complete:
---

# Arquivos

> $\textit{Definição.}$ 

- **Modo texto**: O arquivo é dividido em linhas e as linhas em caracteres.
- **Modo binário**: O arquivo é uma sequência de bytes.

```java
private static void escreverTexto() throws IOException {
	Scanner ler = new Scanner(System.in);
	int i, n;
	System.out.printf("Informe um número: ");
	n = ler.nextInt();
	FileWriter arg = new FileWriter("tabuada.txt");
	arq.write("+--Resultado--+\n");
	for (i = 1; <= 10; ++i) {
		arq.write(String.format("| %2d x %d = %2d |\n", i, n(i*n)))
	}
	arq.write("+--------------+\n");
	arq.close();
}
```