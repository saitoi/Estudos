---
aliases:
  - heap_binaria
tags:
  - ED/Árvores
date: 2023-10-19
time: 13:09
complete:
---
# Heap Binária

> $\textit{Definição.}$ Estrutura de dados baseada em uma árvore binária completa em que todos os nós obedecem a propriedade de heap e cujos nós do último nível estão mais à esquerda possível.

- **Propriedade de heap de mínima: Se $u$ é pai de $v$, então $chave(u)\leq chave(v)$.

Ademais, podemos entender uma heap binária como uma lista de prioridades com três operações primordiais:

- `insere()`: Insere o novo nó mais à esquerda possível da árvore e verificamos se a inserção satisfaz a **propriedade de heap mínima**.
- `achaMinimo()`: Identifica o nó com a menor chave da árvore que **corresponde à raiz da heap**.
- `removeMinimo()`: Remove a raiz da heap binária e realiza processo de **descer**.

> [!info] Vetor $\times$ Árvore Binária
Embora a representação de uma heap envolva uma árvore, utilizamos um **vetor de alocação sequencial** para representar a heap binária.

Aqui está um exemplo de uma heap binária sendo representada tanto por uma árvore binária quanto por um vetor de alocação sequencial.

![[Heap Binária.svg]]

Para identificar o pai de algum nó em um vetor de alocação sequencial, faremos o seguinte cálculo:

1. $pai(i)=\dfrac{\lfloor(i-1)\rfloor}{2}$.
2. $fesq(i)=2i+1$.
3. $fdir(i)=2i+2$.

- [i] Vale ressaltar que iniciamos a contagem a partir do índice 0. Caso começarmos a partir do 1 teríamos uma fórmula diferente.

De antemão, para trabalharmos com uma heap binária precisaremos inicializar ela de modo que o tamanho, a alocação inicial e o número de elementos deverão ser inicializados. Para isso, o seguinte pseudocódigo é válido:

```c
inicializar(heap, tam, ) {
	tam = TAM
	nelem = 0
	heap = aloca()
}
```

## $\texttt{Inserção.}$

Durante a inserção em uma heap binária, um novo nó é adicionado à esquerda no último nível da árvore. Após a adição, é verificado se a nova chave mantém a propriedade de heap mínima. Se não, o nó é movido para cima, trocando-o com seus pais até que a ordem correta seja estabelecida. Essa ação garante a hierarquia e a **propriedade de heap mínima**.

O pseudocódigo referente ao processo de inserção será descrito abaixo:

```c
insere(heap, tam, nelem, x) {
	se (nelem == tam) {
		overflow()
	}
	se (nelem < tam) {
		heap[nelem] = x
		subir(nelem)
		nelem++
	}
}
```

Como veremos posteriormente, a complexidade da inserção é $\mathcal{O}(\log n)$ em função do processo de "subir" caso precisarmos realizar alguma correção na heap. Outrossim, o processo de `overflow()` possui complexidade , ou seja, caso ele for necessário a complexidade total do `inserir()` será ainda maior.

## $\texttt{Subir.}$

Ao realizar a inserção de um novo nó de modo que $chave(filho)>chave(pai)$, aplicaremos o algoritmo para "subir", ou seja, teremos que comparar a chave recém inserida com a chave do pai e trocar caso necessário. Para que isso ocorra, chamaremos o algoritmo recursivamente, até que todos os nós satisfaçam a propriedade de heap mínima.

Suponha que desejamos inserir a chave "25" na árvore anterior.

![[Inserção Heap Binária.svg|300]]

Caso fosse necessário, teríamos que trocar o "25" com as chaves dos nós pais, no entanto, isso não é preciso.

Posto isso, o pseudocódigo referente ao algoritmo de subir será descrito abaixo:

```c
subir(heap, pos) {
	se (pos != 0) {
		pai = PAI[pos]
		se (heap[pai] > heap[pos]) {
			tmp = heap[pos]
			heap[pos] = heap[pai]
			heap[pai] = tmp
			subir(heap, pai)
		}
	}
}
```

O algoritmo descrito acima é **recursivo**. Se desejarmos fazer uma versão não recursiva teremos:

```c
subir(heap, pos) {
	valor = heap[pos]
	enquanto (pos != 0) {
		pai = PAI[pos]
		se (heap[pai] > valor) {
			heap[pos] = heap[pai]
			pos = pai
		} senão break;
	}
	heap[pos] = valor
}
```

Aqui está **outra possibilidade** de para a função de `subir()` não recursiva:

```c
subir(heap, pos) {
	se (pos != 0)
		x = heap[pos]
		enquanto (pos != 0 e heap[PAI(pos)] < x) {
			heap[pos] = heap[PAI(pos)]
			pos = PAI(pos)
		}
		heap[pos] = x
}
```

A complexidade do algoritmo de subir é $\mathcal{O}(\log n)$, uma vez que, no pior caso, o número máximo de comparações seria equivalente à altura da raiz que possui ordem $\log n$ por ser completa.

## $\texttt{Remove mínimo.}$

O processo de remoção em uma heap envolve a remoção da raiz, isto é, nó com a chave mínima da árvore completa. Para tanto, trocamos a chave da raiz com a do última elemento e, posteriormente, chamamos o algoritmo de `descer()` que corresponde ao "inverso" do `subir()` de modo que ambos envolvem a troca das chaves entre os nós

O pseudocódigo referente a esse procedimento pode ser encontrado abaixo.

```c
RemoveMin(heap, nelem) {
	se (nelem > 0) {
		nelem -= 1
		x = heap[0]
		heap[0] = heap[nelem]
		descer(heap, nelem, 0)
	}
}
```

Aqui vai outra possibilidade para remover o elemento mínimo de uma heap binária.

```c
RemoveMin(heap, nelem) {
	nelem--
	heap[0] = heap[nelem]
	descer(heap, nelem, 0)
}
```

## $\texttt{Descer.}$

Ao tentarmos remover o elemento mínimo, inicialmente apenas trocamos as chaves do último com a raiz e chamamos esse processo de `descer()` que, como foi dito, possui a mesma funcionalidade do `subir()` porém descendo a árvore ao invés de subir a mesma.

O pseudocódigo referente ao algoritmo de descer pode ser encontrado abaixo.

```c
descer(heap, nelem, pos) {
	posFilho = Fesq(pos)
	se (posFilho < nelem) {
		posFilhoDir = posFilho + 1
		se (posFilhoDir < nelem) {
			se (heap[posFilhoDir] < heap[posFilho]) {
				posFilho = posFilhoDir
			}
		}
			/* posFIlho é pos do menor filho */
		se (heap[pos] > heap[posFilho]) {
			tmp = heap[pos]
			heap[pos] = heap[posFilho]
			heap[posFilho] = tmp
			descer(heap, nelem, posFilho)
		}
	}
}
```

## $\texttt{Heap Sort.}$

O Heap Sort corresponde ao algoritmo de ordenação baseado na estrutura de dados de heap. Ele recebe um dado vetor e ordena seus elementos de modo que seus **elementos estejam em ordem crescente** e **forme uma heap**. Inicialmente, trataremos do `heapfy()` para converter um vetor qualquer em uma estrutura de heap válida e, adiante, veremos a "real ordenação" de cada chave nessa heap.

Posto isso, o pseudocódigo referente ao `heapfy` pode ser descrito abaixo:

```c
heapfy(vetor, nelem) {
	para (i de 0 até nelem-1) {
	subir(vetor, i)
	}
}
```

Como a complexidade do algoritmo de `subir()` é $\mathcal{O}(\log n)$ e realizamos ao total $n$ repetições, a complexidade total do `heapSort()` corresponde a $\mathcal{O}(n \log n)$. No entanto, também podemos realizar um algoritmo mais eficiente ao utilizarmos o `descer()` no lugar do `subir()` de modo que teremos:

```c
heapfy(vetor, nelem) {
	para (i de PAI(nelem-1) até 1) {
		descer(vetor, nelem, i) 
	}
}
```

Esse último algoritmo, por sua vez, possui complexidade $\mathcal{O}(n)$.

Tendo visto o `heapfy()`, podemos tratar do `HeapSort()` como combinado. Posto isso, aqui está o algoritmo do `HeapSort()`:

![[Heap Binária, Heap Sort, Radix Sort.mp4]]

```c
HeapSort(vetor, nelem) {
	heapfy(vetor, nelem)
	pos = nelem-1
	enquanto(pos > 0) {
		valor = vetor[0]
		vetor[0] = vetor[pos]
		desce(vetor, 0, pos)
		pos--
	}
}
```

Se analisarmos a complexidade total do algoritmo teremos que:

1. O `heapfy()` possui complexidade total de $\mathcal{O}(n)$ se utilizarmos o descer nesse caso.
2. O bloco de repetição `enquanto()` possui complexidade total de $\mathcal{O}(n \log n)$.  

## $\texttt{Subir.}$

Função recursiva para subir na heap binária.

```c
subir(H, pos)
	se pos > 0
		pai = PAI(pos)
		se H[pos] < H[pai]
			x = H[pos]
			H[pos] = H[pai]
			H[pai] = x
			subir(H, pai)
```

Função fechada para subir na heap binária.

```c
subir(H, pos)
	se pos != 0
		x = H[pos]
		enquanto (pos != 0 e H[PAI(pos)] < x)
			H[pos] = H[PAI(pos)]
			pos = PAI(pos)
		H[pos] = x
```

Complexidade: $\mathcal{O}(n\log n)$

## $\texttt{Descer.}$

```c
desce(H, nelem, pos)
	posFilho = FESQ(pos)
	se posFilho < nelem
		menorFilho = H[posFilho]
		se (posFilho + 1) < nelem
			se H[posFilho] < menorFilho
				posFilho++
				menorFilho = H[posFilho]
			se H[pos] > menorFilho
				H[posFilho] = H[pos]
				H[pos] = menorFilho
				desce(H, nelem, posFilho)
```

## $\texttt{Inserção.}$

```c
insere(H, nelem, tam, x)
	se nelem == tam
		overflow()
	se nelem < tam
		H[nelem] = x
		subir(H, nelem)
		nelem++
```

- [i] O algoritmo do `Heap Sort` para a transformação de um vetor qualquer em Heap binária consiste em aplicar a função `subir(V,i)` para cada elemento do vetor desordenado como abaixo.

```c
para i de 1 até nelem-1
	subir(V, i)
```

Complexidade: $\mathcal{O}(n \log n)$

Podemos fazer de uma forma melhor:

```c
para i de nelem-1 até 0
	descer(i)
```

Complexidade: $\mathcal{O}(n)$

## $\texttt{Heap Sort.}$

```c
heapSort(V, nelem)
	criaHeap(V, nelem)
	enquanto (nelem > 1)
		nelem--
		tmp = V[0]
		v[0] = v[nelem]
		desce(V, nelem, 0)
```

Complexidade: $\mathcal{O(n \log n)}$, a função `desce(V, nelem, 0)` possui complexidade $\mathcal{\log n}$.
