---
aliases:
  - hash_table
tags:
  - ED
date: 2023-11-09
time: 13:54
complete:
---
![[hash1.jpg]]
![[hash2.jpg]]

# Hash

> $\textit{Definição.}$ Estrutura de dados que armazena informações de forma associativa, permitindo a rápida recuperação de dados com base em uma chave. Ela utiliza uma função de hash para mapear chaves para posições na tabela, onde os dados são armazenados.

Para realizar o mapeamento de cada chave em uma posição do vetor, empregamos uma **função de hash**. Nesse sentido, é útil que uma função de hash respeite duas propriedades:

1. Rápida de calcular.
2. Possuir distribuição uniforme, isto é, $prob(h(x)=k)=\dfrac{1}{m}$ em que $m$ representa o número de posições do vetor.

- [i] Em uma tabela hash, não são permitidas duplicatas, ou seja, a inserção de dois elementos idênticos. Nesse caso, apenas um deles será inserido de fato.

## $\texttt{Tipos de Hash.}$

Dentre os principais tipos de hash, podemos destacar:

- **Com encadeamento exterior**: Usa a memória fora da tabela para alocar dados (para as listas encadeadas).
- **Com encadeamento interno**: A alocação é realizada no próprio vetor sequencial.
- **Com encadeamento interno e com/sem área de colisão**: Podemos designar ou não uma região específica do vetor para tratar das colisões.
- **Com encadeamento interno e com/sem coalescência**: A coalescência permite os elementos sejam colocados nas próximas posições disponíveis (sem nenhuma ordem). A ausência de coalescência exige que os elementos sejam colocados nos índices corretos da tabela hash.

De antemão, aqui estão algumas funções gerais úteis para quando formos tratar dos diversos tipos de encadeamento:

- **Estrutura básica**:

```c
typedef struct node {
	int chave;
	struct node* prox;
} Node;
```

- **Função hash**: De modo a simplificar a função hash, utilizamos uma `chave` inteira e efetuamos a operação modular com `tam` sobre ela.

```c
int h(int chave, int tam) {
	return hash(chave) % tam;
}
```

### $\texttt{Com Encadeamento Externo.}$

Refere-se a uma técnica de resolução de colisões em tabelas hash, onde cada slot da tabela armazena uma estrutura de dados (como uma lista encadeada ou árvore) para lidar com múltiplos elementos que colidem no mesmo índice da tabela de dispersão.

- **Inicialização da tabela**

```c
void inicializacao(Node*** tabela, int *tam, int TAM) {
    (*tabela) = (Node**)malloc(sizeof(Node*) * TAM);
    *tam = TAM;
}
```

- **Busca**: A função de `busca()` é simples e se baseia no princípio de calcular o hash da chave `int x` passada como parâmetro de modo a obter o índice daquele elemento na tabela hash. Com isso, percorremos a lista encadeada referente àquela posição da tabela e verificamos a existência ou não da chave.

```c
Node* busca(int H[], int x) {
	int pos = h(x);
	Node* pt = H[pos];
	while (pt != NULL && pt->chave != x) {
		pt = pt->prox;
	}
	return pt;
}
```

- **Inserção**: A função responsável por inserir um novo nó na posição correta da tabela hash implementa o algoritmo de busca descrito anteriormente para **verificarmos se o elemento já existe ou não**. Feito isso, caso o elemento não exista, alocamos um nó para ele e inserimos-o no início da lista encadeada referente àquela posição da tabela.

```c
void insere(int H[], int x) {
	Node* aux = busca(H, x);
	if (aux == NULL) {
		aux = (Node*) malloc(sizeof(Node));
		aux->chave = x;
		int pos = h(x);
		aux->prox = H[pos];
		H[pos] = aux;
	}
}
```

## $\texttt{Encadeamento Interno e Com Área de Colisão.}$

**Ideia central**: 

De antemão, precisamos ter em mente algumas definições importantes para esse tipo de hash, aqui estão:

```c
#DEF LIVRE 0
#DEF OCUPADO 1

/* 
prox == -1 <=> prox == NULL
prox == -2 <=> posicao livre
*/
```

- **Inicialização**: Diferentemente da tabela hash com encadeamento externo, nesse tipo de estrutura não precisamos de uma lista encadeada em cada posição do vetor tal qual a forma abaixo:

```c
void inicializar(Node **tabela, int tam, int *led) {
	*tabela = (Node**) malloc(sizeof(Node)*tam*2);
	*led = tam;
    for (int i = 0; i < tam - 1; ++i) {
        tabela[i].prox = -2;
    }
    for (int i = tam; i < 2 * tam - 2; ++i) {
        tabela[i].prox = i + 1;
    }
    tabela[2 * tam - 1].prox = -1;
}
```

- **Posição Livre**: Como foi demonstrado anteriormente, empregamos o indicador "-2" para designar que uma posição se encontra livre na tabela hash.

```c
int pos_livre(tabela, pos) {
	return tabela[pos].prox == -2;
}
```

- **Busca**: Começamos calculando a posição da chave na tabela hash usando a função `h(x, tam)`. Em seguida, marcamos a variável `p` como -1 para indicar "posição vazia" e verificamos se a posição que desejamos inserir está ocupada. Se não estiver vazia, percorremos sequencialmente a lista encadeada na área de colisão, verificando se atingimos o final da lista (`p == -1`) ou se encontramos a chave desejada (`tabela[p].chave != x`).

```c
int busca(tabela, tam, x) {
	pos = h(x, tam);
	p = -1;
	if (!pos_livre(tabela, pos)) {
		p = pos;
		while (p != -1 && tabela[p].chave != x) {
			p = tabela[p].prox;
		}
	}
	return p;
}
```

- **Insere**: 

1. **Cálculo da posição na tabela hash:**
   - Calcula a posição `pos` da chave na tabela hash usando a função `h(x, tam)`.

2. **Busca pela chave na tabela:**
   - Executa uma busca na tabela para encontrar a chave `x` usando a função `busca(tabela, tam, x)`, armazenando o resultado em `p`.

3. **Inserção da chave na tabela:**
   - Se a chave não foi encontrada (`p == -1`):
     - Verifica se a posição `pos` na tabela está livre usando `pos_livre(tabela, pos)`.
     - Se estiver livre, insere a chave `x` na posição `pos` da tabela com a marcação de fim da lista (`tabela[pos].prox = -1`).
     - Caso contrário, procura por uma nova posição (`novaPos`) na lista de áreas de colisão (`led`).
     - Se não houver nova posição disponível (`novaPos == -1`), executa uma função de tratamento de overflow (`overflow()`).
     - Senão, utiliza a nova posição `novaPos` na tabela para inserir a chave `x` e atualiza os ponteiros necessários.

Esse algoritmo tenta inserir uma chave `x` na tabela hash. Se a posição inicial estiver livre, a chave é inserida lá. Caso contrário, a função procura por uma nova posição na lista de áreas de colisão para inserir a chave, lidando com colisões através do encadeamento interno.

```c
void insere(tabela, x, tam, led) {
	pos = h(x, tam);
	p = busca(tabela, tam, x);
	if (p == -1) {
		if (pos_livre(tabela, pos)) {
			tabela[pos].chave = x;
			tabela[pos].prox = -1;
		} else {
		novaPos = led;
		if (novaPos == -1) {
			overflow();
		}
		led = tabela[novaPos].prox;
		tabela[pos].prox = novaPos;
		tabela[novaPos].chave = x;
		}
	}
}
```

- **Remove**: 

```c
void remove(tabela, x, tam) {
	pos = h(x, tam);
	if (!pos_livre(tabela, pos)) {
		p = pos;
		ant = -1;
		while (p != -1 && tabela[p].chave != x) {
			ant = p;
			p = tabela[p].prox;
		}
		if (p != -1) {
			if (p == pos) {
				if (tabela[pos].prox == -1) {
					tabela[pos].prox = -2;
				} else {
					pprox = tabela[pos].prox;
					tabela[pos].chave = tabela[pprox].chave;
					tabeal[pos].prox = tabela[pprox].prox;
					devolve(tabela, led, pprox);
				}
			} else {
				tabela[ant].prox = tabela[p].prox;
				devolve(tabela, led, p);
			}
		}
	}
}

void devolve(tabela, led, p) {
	tabela[p].prox = led;
	led = p;
}
```

## $\texttt{Com Encadeamento Interno e Sem Área de Colisão.}$



### $\texttt{Hash Uniforme.}$

$h:U\to[0,m-1]$

$\textup{prob}(h(x)=k)=\dfrac{1}{m}$
