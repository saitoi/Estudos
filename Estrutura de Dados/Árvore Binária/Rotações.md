---
aliases:
  - tree_rotations
tags:
  - ED
date: 2023-09-23
time: 18:34
complete:
---

# $\texttt{Rotação.}$

## $\texttt{Rotação direita.}$

![[Rotação Esquerda.jpg | 550]]

```c
void rotacaoDireita(No *noPai) {
	No *noFilho = noPai->esquerda;
	if (noFilho->esquerda->altura > noFilho->direita->altura) {
		noPai->esquerda = noFilho->direita;
		noFilho->direita = noPai;
		noFilho->altura = altura(noFilho->esquerda->altura, noFilho->direita->altura);
		noFilho->altura = altura(noPai->esquerda->altura, noPai->direita->altura);
		noPai = noFilho;
	} else {
		
	}
}
```