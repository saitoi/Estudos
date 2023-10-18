---
alias: const
tags: C＋＋
date: 2023-08-03
time: 20:43
---

# Constantes

> $\textit{Definição.}$ Refere-se a um valor que não pode ser alterado após a atribuição e, portanto, são valores fixos e imutáveis no decorrer da execução do programa.

- Constantes literais: Valores fixos e imutáveis que aparecem diretamente no código-fonte do programa.
1. Literais numéricos:
```cpp
int age = 18;
double pi = 3.14;
```
2. Literais de caracteres:
```cpp
char letra = 'A';
char newline = '\n';
```
3. Literais de strings:
```cpp
std::string nome = "Pedro";    
```
4. Literais booleanos:
```cpp
bool verdadeiro = true;
bool falso = false;
```

- Constantes declaradas: Valores constantes definidos pela palavra-chave `const`.
```cpp
const double pi {3.1415926};
const int meses_no_ano {12};
```

- Constantes definidas: Definidas utilizando a diretiva de pré-processamento `#define`.
```cpp
#define pi 3.1415926
#define meses_no_ano 12
```
