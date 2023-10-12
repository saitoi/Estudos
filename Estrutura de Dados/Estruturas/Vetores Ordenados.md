![[Inserção.jpeg| 750]]
![[Remoção.jpeg| 750]]
![[Busca e Inicialização.jpeg| 750]]

```c
void inicializar(int *v, int *tam, int *nelem) {
	int tam = 10, nelem = 10;
	v = (int  *) malloc(sizeof(int)*tam);
}

void busca(int *v, int nelem, int x) {
	int i = 0;
	while (v[i] < x && i < nelem) ++i;
	return i;
}

void insere(int *v, int *nelem, int *tam, int x) {
	int pos = busca(v, *nelem, x);
	if (pos == *nelem && v[pos] != x)
		overflow(v, tam);
	if (pos < *nelem && v[pos] == x) {
		puts("Já consta");
		return;
	}
	for (i = *nelem; i > pos; --i)
		v[i] = v[i-1];
	v[pos] = x;
	(*nelem)++;
}

void remove(int *v, int *nelem, int x) {
	int pos = busca(v, *nelem, x);
	int i = 0;
	if (pos == *nelem || v[pos] != x) {
		puts("Elemento não foi encontrado");
		return;
	}
	if (pos < *nelem && v[pos] == x) {
		for (i = pos; i < *nelem-1; ++i)
			v[i] = v[i+1];
		(*nelem)--;
	}
}
```

## $\texttt{Refazendo.}$

```c
vazio inicializar(int *arr, int *nelem, int tam)
	*nelem = 0
	arr = aloca(vetor[tam])

vazio overflow(int *arr, int *tam)
	arr = realoca(vetor[tam*2])

int busca(int *arr, int *nelem, int x)
	int indice
	enquanto(x > arr[indice] e indice < *nelem)
		++indice
	retorna indice

vazio insere(int *arr, int *nelem, int *tam, int valor)
	int pos = busca(arr, nelem, valor)
	se (arr[pos] == valor e pos < *nelem)
		Imprime("Já existe")
		retorna;
	se (*nelem == *tam)
		overflow(arr, tam)
	para i de *nelem até pos
		arr[i] = arr[i-1]
	arr[pos] = valor
	(*nelem)++

vazio remove(int *arr, int *nelem, int valor)
	int pos = busca(arr, nelem, valor)
	se (*nelem == 0)
		underflowErro()
		retorna;
	se (pos == *nelem ou arr[pos] != valor)
		Imprime("Valor não encontrado")
	senão
		para i de pos até *nelem-1
			arr[i] = arr[i+1]
		(*nelem)--
```

