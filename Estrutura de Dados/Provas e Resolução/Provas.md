---
aliases:
  - provas
  - resolucao
tags:
  - ED
date: 2023-09-17
time: 00:36
complete: false
---
### Nome: Pedro Henrique Honorio Saito

### DRE: 122149392

# $\texttt{Prova 2018}$

![[Prova 2018.jpg | 650]]

# $\texttt{Resolução da Prova 2018}$

#### 1. Algoritmo em C de remoção de uma chave $x$ de uma lista encadeada com nó cabeça. ^9aa38b

```c
void removeChave(No **cabeca, int chave) {
	No *auxiliar = *cabeca;
	No *anterior = NULL;
	
	while(auxiliar != NULL) {
		if(auxiliar->data == chave) {
			anterior->proximo = atual->proximo;
			free(atual);
			return;
		}
		anterior = auxiliar;
		auxiliar = anterior
	}
	puts("Chave não foi encontrada");
}
```

$\textbf{Explicação.}$ São criados dois ponteiros, um referente ao nó atual e outro designando o nó anterior. A lista é percorrida até chegarmos ao nó com o conteúdo $\textit{chave}$ desejado ou até chegarmos ao fim da estrutura. Posto isso, verificamos se a $\textit{chave}$ foi encontrada e, caso positivo, temos dois casos possíveis, sendo estes: ^d140a5

1. Nó removido é cabeça da lista. ^5a0ee6
2. Nó removido não é cabeça.

No primeiro caso, apenas atualizamos o ponteiro atual para o próximo elemento da lista. Em contrapartida, no segundo caso fazemos o ponteiro anterior apontar para o nó apontado pelo atual, ou seja, o elemento "pulando" o elemento a ser removido. Por fim, a memória do ponteiro atual é liberada.
#### $\;$
***

#### $\textup{2.1.}$ Algoritmo eficiente que preenche para cada nó da árvore, o campo `no->numDesc` ("número de descendentes") indicativo do número de chaves da subárvore fixada naquele nó.

```c
int calculaNumDescendentes(struct No *raiz) {
	if (raiz == NULL) {
		return 0;
	}
	
	int esquerdaDescendentes = calculaNumDescendentes(raiz->esquerda);
	int direitaDescendentes = calculaNumDescendentes(raiz->direita);
	
	raiz->numDesc = esquerdaDescendentes + direitaDescendentes;
	
	return raiz->numDesc + 1;
}
```

$\textbf{Explicação.}$ O algoritmo para calcular o número de descendentes de todos os nós é recursivo e itera sobre cada nó, dividindo-o em esquerda e direita. Inicialmente, verificamos se o nó atual é nulo e retornamos zero se for o caso. Por conseguinte, chamamos recursivamente a função para duas variáveis inteiras, `esquerdaDescendentes` e `direitaDescendentes` as quais armazenam a quantidade de descendentes para cada lado do nó. Feito isso, atribuímos a soma desses valores ao campo `numDesc` da raiz atual e, por fim, retornamos esse atributo acrescido de $1$ (para contabilizar ele mesmo). Aqui está um exemplo:
```tikz
\begin{document}
\begin{tikzpicture}[scale=1.2]
  % Nó raiz
  \node {10}
    % Filhos esquerdo e direito
    child {node {5}
      child {node {3}
        child[missing] {} % Nó vazio para manter o espaço
        child {node {1}}
	        child {node {$\vdots$}
		        child {node {20}}
		        }
	        child[missing] {}
      }
      child[missing] {} % Nó vazio para manter o espaço
    }
    child {node {20}
      child {node {15}
        child[missing] {}
	    child {node {$\vdots$}
	      child {node {31}}
	      }
      }
      child {node {25}}
    };
\end{tikzpicture}
\end{document}
```

Considerando a árvore binária acima, a função `calcularNumDescendentes` iniciaria recebendo o endereço da raiz $10$ e, para determinar a quantidade de descendentes, seria chamada recursivamente para cada nó da árvore. Desse modo, ao alcançar o elemento `NULL` a função começaria a retornar e incrementar uma unidade ao campo `numDesc` de cada nó.

***

#### $\textup{2.2}$ Algoritmo eficiente para o procedimento `select(k)` que retorna a k-ésima menor chave da árvore binária, usando o campo `numDesc` mencionado.

```c
int select(No *raiz, int k) {
	if (raiz == NULL)
		return -1;
	int posRaiz;
	if (raiz->esquerda == NULL) posRaiz = 0;
	else posRaiz = raiz->esquerda->numDesc + 1;
	if (posRaiz == k) return posRaiz;
	return (posRaiz < k) ? select(raiz->esquerda, k) : select(raiz->direita, k - posRaiz - 1);
}
```

***



# $\texttt{Prova 2016}$

![[Prova 2016.jpg | 650]]

# $\texttt{Resolução da Prova 2016}$

#### 1. Algoritmos em C de busca e inserção de um nó em uma lista duplamente encadeada, ordenada com nó cabeça. Em um primeiro momento, aqui está o algoritmo de inserção na lista duplamente encadeada.

```c
inserirOrdenado(No *cabeca, inteiro data)
	No *novoNo = aloca(No)
	
	se novoNo == NULL
		erro
	
	novoNo->data = data
	No *noAtual = cabeca->proximo
	enquanto (noAtual != NULL e data > noAtual->data)
		atual = atual->proximo;
	se atual == NULL
		No *ultimoNo = cabeca
		enquanto (ultimoNo->proximo != NULL)
			ultimoNo = ultimoNo->proximo
		novoNo->proximo = NULL
		novoNo->anterior = ultimoNo
		ultimoNo->proximo = novoNo
	senão
		novoNo->proximo = noAtual
		novoNo->anterior = noAtual->anterior
		noAtual->anterior->proximo = novoNo
		noAtual->anterior = novoNo
```
#### $\;$
Por fim, aqui está o algoritmo de busca que identifica o nó por meio de sua chave.

```c
Node *buscaNo(Node *cabeca, int alvo) {
	Node *noAtual = cabeca->proximo;
	while (noAtual != cabeca) {
		if (noAtual->data == alvo) return noAtual;
		noAtual = noAtual->proximo;
	}
	return NULL;
}
```
#### $\qquad$
$\texttt{Preciso mudar essa explicação.}$

$\textbf{Explicação.}$ O algoritmo de inserção do nó é composto por duas funções, uma responsável por alocar memória para um novo nó, enquanto a outra apenas insere a estrutura recém alocada para o início da lista. A criação do nó feita pela função `No *criarNo(int data)` que recebe como parâmetro o identificador numérico (data) que será atribuído ao nó. 

Por outro lado, a função `No *insereNo(No *cabeca, int data)` chama o método anterior por meio do parâmetro da chave e realiza a modificação de cada ponteiro sequencialmente para a inclusão da nova estrutura.

A atualização dos ponteiros segue os passos abaixo:

1. Campo **próximo** do `novoNo` passa a apontar para elemento que sucede o cabeça.
2. Campo **anterior** do `novoNo` passa a apontar para o cabeça.
3. Se houver um nó à frente do cabeça, o campo **anterior** deste passará a apontar para o `novoNo`.
4. Campo **próximo** do cabeça passa a apontar para `novoNo`.
#### $\;$
Finalmente, temos que tratar do algoritmo de busca da lista duplamente encadeada. Como podemos perceber, a função `buscaNo(int data)` inicia declarando o ponteiro `noAtual` que identifica o elemento analisado na lista. Assim sendo, percorremos a lista sequencialmente e verificamos se encontramos o elemento desejado por meio do identificador `data` até alcançarmos o cabeça novamente. Caso o nó seja encontrado, retornamos seu endereço que corresponde ao `noAtual` e, caso contrário, retornamos `NULL`.

***

2. $1.$ Dada uma árvore binária de busca com raiz apontada por `ptraiz` em que cada nó contém os campos `esq`, `dir`, `chave` e `altura`. O algoritmo de inserção de uma chave $x$ está descrito na seção de [[Árvore Binária]], 

```c

```

# $\texttt{Prova 2010.1}$

![[Prova 2010 1.jpg | 650]]

1. 1 O algoritmo de inserção de um nó em uma lista duplamente encadeada e ordenada com nó cabeça pode ser encontrado em [[Lista Duplamente Encadeada]], no entanto tentarei replicá-lo em pseudocódigo

```c
No *busca(No *primeiro, int valor)
	enquanto (primeiro != NULL e valor > primeiro->chave)
		primeiro = primeiro->proximo

vazio insereOrdenado(No *cabeca, int valor)
	No *novo = aloca(No)
	se novo == NULL
		Imprime("Erro ao alocar memória.");
		retorne
		
	novo->chave = valor
	No *atual = busca(cabeca->proximo)
		
	novo->proximo = atual
	se atual == NULL
		No *ultimo = cabeca
		enquanto (ultimo->proximo != NULL)
			ultimo = ultimo->proximo
		novo->anterior = ultimo
		ultimo->proximo = novo
	senão
		novo->anterior = atual->anterior
		atual->anterior->proximo = novo
		atual->anterior = novo
```

$\textbf{Explicação.}$ 

1.2 O algoritmo de inserção da questão anterior possui complexidade $\mathcal{O}(n)$ pois, no pior caso, a busca será realizada até o último elemento, isto é, até alcançarmos o enésimo termo na estrutura de dados de tamanho $n$.

2.1 

```c
int somaChaves(No *raiz)
	se raiz == NULL
		retorne 0
	senão
		raiz->soma = somaChaves(raiz->esquerda) + somaChaves(raiz->direita)
		return (raiz->soma + raiz->chave)
```