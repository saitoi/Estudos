---
alias: encapsulamento herança polimorfismo
tags: java/✖
date: 2023-08-14
time: 11:40
---

# Noções Básicas de Programação Orientada a Objetos (POO)

> $\textit{Definição.}$ Alguns conceitos fundamentais deste modelo de programação incluem: Encapsulamento, polimorfismo e herança. Irei explicar com mais detalhes cada um dos conceitos abaixo.

1. **Encapsulamento.** ^c6cdc7
	- Envolve a ideia de agrupar dados (atributos) e operações (métodos) em unidades reutilizáveis denominadas [[Classes|classes]]. Posto isso, a ideia é limitar o acesso direto aos detalhes internos de uma classe, restringindo a interação apenas às interfaces públicas (métodos públicos).

2. **Herança.** ^a09fda
	- Permite a criação de subclasses (classes derivadas) baseadas em classes existentes. Desse modo, a subclasse herda os atributos e métodos da superclasse, evitando a repetição de código e estabelecendo hierarquia de classes.
	- As subclasses criadas podem adicionar atributos e métodos específicos, restritos a essa classe.
	- Em Java, não é possível que uma classe herde mais de uma classe.
##### $\;$
3. **Polimorfismo.**
	- Refere-se à capacidade de objetos de diferentes classes serem tratados de forma uniforme por meio de interfaces comuns, havendo dois tipos de polimorfismo: ^4b82fd ^a99dd0 ^e548ca
	1. **Polimorfismo de sobrecarga (ou estático).**
		- Refere-se à existência de métodos com assinaturas semelhantes, porém se diferenciam pelo número e tipos de parâmetros. Portanto, o programa diferencia os métodos segundo seus argumentos chamados.
		 
	2. **Polimorfismo de sobreposição (ou dinâmico).**
		- Refere-se à substituição de métodos já definidos por uma superclasse. A assinatura deve ser idêntica ao método da superclasse. Normalmente incluímos o indicador `@override` para sinalizar sobrescrita de métodos.
