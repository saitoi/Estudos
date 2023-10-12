---
alias: tamanho_tabela_C_Cpp
tags: ⓒ
---
# Tamanho dos Tipos

> $\textit{Definição.}$ Número de bytes armazenados por cada tipo de variável juntamente do intervalo de valores de cada uma delas.

**Obs.** Para determinar o tamanho de uma variável em bytes, utilizamos a função `sizeof` com parâmetro do nome da variável desejada. A sintaxe é a seguinte: `sizeof(var_nome)`.

|Tipos|Número de Bytes|Valor Mínimo|Valor Máximo|
|---|---|---|---|
|`int`|4|-2,147,483,648|2,147,483,647|
|`unsigned int`|4|0|4,294,967,295|
|`short int`|2|-32,768|32,767|
|`unsigned short int`|2|0|65,535|
|`long`|4 ou 8|-2,147,483,648 (32 bits) ou|2,147,483,647 (32 bits) ou <br> -9,223,372,036,854,775,808 (64 bits)|
|`unsigned long`|4 ou 8|0|4,294,967,295 (32 bits) ou <br> 18,446,744,073,709,551,615 (64 bits)|
|`char`|1|-128|127|
|`unsigned char`|1|0|255|
|`float`|4|1.2E-38|3.4E+38|
|`double`|8|2.3E-308|1.7E+308|
|`long double`|10 ou 16|3.4E-4932 (10 bytes) ou|1.1E+4932 (10 bytes) ou <br> 3.4E-4932 (16 bytes)|
