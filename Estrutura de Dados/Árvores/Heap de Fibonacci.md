---
aliases:
  - heap_fibonacci
tags:
  - ED/Árvores
date: 2023-11-19
time: 11:48
complete:
---
 # Heap de Fibonacci

> $\textit{Definição.}$ Coleção de árvores de Fibonacci, tal que todo nó obedece a propriedade heap (no caso a propriedade de heap mínima).

Semelhante à heap binomial, no entanto possui algumas diferenças primordiais, dentre os quais destacamos:

- Todo nó da heap, ao perder um filho, é marcado (**com exceção da raiz**). Se um nó já marcado perde um filho, então este também será removido da heap.
- **Avaliação tardia**: Os nós vão sendo inseridos como repetidos $B_{0}$ e só serão reorganizados quando houver alguma remoção.

## $\texttt{Implementação.}$

Todo nó de uma heap de Fibonacci possui um ponteiro para o seu pai, para um filho e para ambos os irmãos, isto é, à esquerda e à direita. Outrossim, a heap sempre irá conter um ponteiro para a menor raiz.

## $\texttt{Inserção.}$

É criada uma árvore $B_{0}$ com sua respectiva chave e ela será inserida normalmente na árvore heap atual. Devemos considerar dois casos:

- **Com avaliação tardia**: Adicionamos o nó à lista de raízes e atualizamos o nó de menor chave (se necessário).
- **Sem avaliação tardia**: Adicionamos o nó à lista de raízes e unimos, conforme de costume, as árvores de ordens equivalentes tal qual uma heap binomial.

## $\texttt{Mudança de Prioridade.}$

A mudança de prioridade de um nó em uma árvore de Fibonacci envolve a sua remoção da estrutura e a criação de uma $B_{0}$ com a prioridade desejada. No entanto, devemos lembrar que: **Caso você remova um nó cujo pai já foi marcado, é necessário remover o pai junto e adicioná-lo como uma nova $B_{0}$**.

Aqui está um exemplo de mudança de prioridade do 42 para 2.

*Imagem do resumo da pasta de ED de mudança de prioridade - Anotações em Aula*

## $\texttt{Achar o Mínimo.}$



```c
Node* menorFilho(Node* pt) {
    if (pt == NULL || pt->child == NULL) {
        return NULL;
    }
	
    Node* aux = pt->child;
    Node* menor = aux;
	
    while (aux != NULL) {
        if (aux->key < menor->key) {
            menor = aux;
        }
        aux = aux->sibling;
    }
	
    return menor;
}
```

## $\texttt{Descer.}$

Tendo em vista as semelhanças entre as árvores de Fibonacci com as binomiais, podemos concluir que o processo de `descer()` nesse tipo de estrutura não possui diferença. Entretanto, para facilitar podemos empregar o algoritmo anterior do `menorFilho()` e usá-lo para determinar o menor filho de modo que será necessário apenas realizar a troca.

```c
void desceFibonacci(Node* pt) {
    Node* menor = menorFilho(pt);
	
    if (menor == NULL) {
        return;
    }
	
    if (menor->key < pt->key) {
        int temp = menor->key;
        menor->key = pt->key;
        pt->key = temp;
        desceFibonacci(pt);
		    }
}
```

