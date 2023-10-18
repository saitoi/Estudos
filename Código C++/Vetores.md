---
alias: vectors
tags: C＋＋
date: 2023-08-26
time: 13:49
---

# Vetores 

> $\textit{Def. Vetores.}$ Estrutura de dados dinâmica que permite armazenar uma coleção de elementos de tamanho variável.

**Principais pontos**
- **Redimensionamento dinâmico.** Possibilidade de alterar o tamanho durante a execução do programa.
- **Inserção e remoção eficiente.** Inserção ou remoção do conteúdo das posições de vetores com mais facilidade. 
- **Iteradores.** Ação de percorrer o vetor por meio de iteradores.
- **Métodos.** Métodos da biblioteca `<vector>` para a manipulação de vetores.

## Declaração

Em C++, é necessário incluir a biblioteca de vetores `<vector>` juntamente do namespace padrão por meio do `std::vector` ou simplesmente `using namespace std`.

A declaração é feita especificando o tipo de dado do vetor e seu tamanho inicial (opcional), tal como no exemplo abaixo:
```cpp
std::vector<char> meuVetor;        /* Vetor vazio de char */
std::vector<double> outroVetor(5); /* Vetor de 5 elementos double */
```

## Inicializações

1. **Inicialização vazia (automática).**
	- Ao declarar um vetor sem especificar o tamanho ou valor inicial, ele será inicializado vazio. Aqui está um exemplo:
	```cpp
	std::vector<int> meuVetor; // Vetor vazio
	```

2. **Inicialização com tamanho ou valor padrão.**
	- Ao declarar um vetor, podemos seu tamanho e, por sua vez, ele terá suas posições inicializadas com zero. Por outro lado, podemos especificar um valor padrão para todas as casas, tal como no exemplo abaixo:
	```cpp
	std::vector<int> vetorComTamanho(5);               // Cinco posições inicializadas com zero.
	std::vector<double> vetorComTamanhoEValor(3, 1.5)  // Três posições inicializadas com 1.5
	```

3. **Inicialização com lista de inicializadores.**
	- Podemos especificar uma lista de valores para inicializar o vetor desejado, aqui está um exemplo:
	```cpp
	std::vector<int> vetorLista = {1, 2, 3};
	```

4. **Inicialização com intervalo.**
	- É possível inicializar um "subvetor" a partir de um intervalo especificado do vetor origem, tal como abaixo:
	```cpp
	std::vector<int> subvetor(meuVetor.begin() + 1, meuVetor.end() - 1);
	```

## Inserção e remoção

Para realizar a inserção e remoção de valores no vetor, empregamos os métodos abaixo. De antemão, considere a declaração do seguinte vetor:
```cpp
std::vector<int> meuVetor(3);   // Vetor "meuVetor" inicializado com zero
```

1. `push_back()`: Método destinado à inserção de valores no final do vetor, tal como o exemplo abaixo:
	```cpp
	meuVetor.push_back(1);          // Posição [2] preenchida com 3
	meuVetor.push_back(2);          // Posição [1] preenchida com 2
	// ..
	```

2. `pop_back()`: Método destinado à remoção de valores do final do vetor, tal como abaixo:
	```cpp
	meuVetor.pop_back();            // Posição [2] desocupada
	meuVetor.pop_back();            // Posição [1] desocupada
	```

## Tamanho e iteração

