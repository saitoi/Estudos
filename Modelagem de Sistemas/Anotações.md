---
aliases:
  - ims
tags:
  - IMS
date: 2023-10-10
time: 15:27
complete:
---
# Anotações

Capítulos relevantes:

- $(1).$ Visão geral
- $(4).$ Modelagem de casos de uso
- $(5).$ 

# $\texttt{1.0. Visão Geral.}$

1. Surgimento de um novo tipo de bem econômico: a $\textit{informação.}$ Havendo a necessidade de se gerenciar esse bem de forma adequada e eficiente por meio dos denominados $\textit{sistemas de informação.}$
2. $\textup{Sistemas de informação.}$ Combinação de pessoas, dados, processos, interfaces, redes de comunicação e tecnologia que interagem com o intuito de evoluir o processo de negócio de uma organização empresarial a respeito de suas informações.
3. Um dos principais componentes do sistema de informação é o $\textit{sistema de software.}$ que compreende os módulos funcionais computadorizados com o intuito de proporcionar ao usuário a automatização de várias tarefas no sistema.

## $\texttt{1.1. Modelagem de Sistema de Software.}$

1. Necessidade de se construir $\textit{modelos}$ para lidar com sistemas de software mais complexos. Aqui estão algumas vantagens:
	1. $\textbf{Gerenciamento da complexidade.}$ Permite extrair do sistema os conceitos mais relevantes e administrá-los da melhor forma.
	2. $\textbf{Comunicação entre as pessoas envolvidas.}$ Os modelos do sistema facilitam a difusão de informações relativas ao sistema.
	3. $\textbf{Redução dos custos no desenvolvimento.}$ A criação de um modelo permite evitar a correção de erros custosos, pois erros identificados no modelos têm um impacto menos desastroso do que erros no sistema final.
	4. $\textbf{Previsão do comportamento futuro do sistema.}$ O modelo serve como um $\textquotedblleft$laboratório$\textquotedblright$ que permite prever mudanças que seriam feitos ao sistema final.
2. $\textup{Diagrama.}$ Apresentação de uma coleção de $\textit{elementos gráficos}$ que possuem algum significado predefinido.
3. O diagrama e sua informação textual associada compõem a $\textit{documentação}$ do modelo.

## $\texttt{1.2. O Paradigma da Orientação a Objetos.}$

1. $\textup{Paradigma.}$ *Forma de abordar de um problema.*
2. Fundamentos do paradigma da orientação a objetos propostos por Alan Kay:
	1. Qualquer coisa é um objeto.
	2. Objetos realizam tarefas por meio da requisição de serviços a outros objetos.
	3. Cada objeto pertence a uma determinada $\textit{classe}$. Classes agrupam objetos similares.
	4. A classe é um repositório para o comportamento do objeto.
	5. Classes são dispostas em hierarquias.
3. A orientação a objetos visualiza o sistema de software como uma coleção de agentes interconectados denominados $\textit{objetos}$. O objetivo dos objetos é realizar alguma tarefa específica por meio da interação com outros objetos.

### $\texttt{1.2.1. Classes e Objetos.}$

1. Na terminologia da orientação a objetos, cada ideia é denominada de $\textit{classe}$. Pode-se entender as classes como $\textit{moldes}$ a partir dos quais os objetos são construídos.
2. A classe é uma $\textit{abstração}$ das características de um grupo de coisas do mundo real. Para fins de modelagem de sistemas, devemos considerar apenas as características $\textit{relevantes}$ para a formação da classe.

### $\texttt{1.2.2. Operação, Mensagem e Estado.}$

1. $\textup{Operação.}$ Ação que um objeto é capaz de realizar quando solicitado.
2. Objetos respondem aos estímulos que lhe são enviados, dizemos que o objeto está recebendo uma $\textit{mensagem}$ requisitando alguma operação.
3. $\textup{Estado.}$ Conjunto de valores de seus atributos em um dado momento que **pode** ser alterada no recebimento de uma mensagem.

### $\texttt{1.2.3. O Papel da Abstração na Orientação a Objetos.}$

*Não é importante assim..*

#### $\texttt{1.2.3.1. Encapsulamento.}$

Abordado em mais detalhe em <ins>Noções básicas de POO</ins>, aqui está uma prévia.

![[Noções Básicas de POO#^c6cdc7]]

#### $\texttt{1.2.3.2. Polimorfismo.}$

Aqui está uma prévia abaixo.
![[Noções Básicas de POO#$ ;$]]

#### $\texttt{1.2.3.3. Generalização (Herança)}$

Por fim, aqui vai a última prévia.

![[Noções Básicas de POO#^a09fda]]

#### $\texttt{1.2.3.4. Composição.}$

1. Princípio da composição afirma que objetos podem ser $\textit{compostos}$ de outros objetos, isto é, revela a possibilidade de criação de novos objetos a partir da reunião de outros objetos.
2. Semelhante ao princípio da herança (generalização).

## $\texttt{1.3. Evolução Histórica da Modelagem de Sistemas.}$
*Nada de interessante por aqui..*

## $\texttt{1.4. A Linguagem de Modelagem Unificada (UML).}$
1. $\textup{Linguagem de Modelagem Unificada (UML).}$ *linguagem visual* para modelagem de sistemas por meio da definição de elementos gráficos que representam os conceitos do paradigma da orientação a objetos.
2. Cada elemento gráfico possui uma $\textit{sintaxe}$ e uma $\textit{semântica}$.
	1. $\textup{Sintaxe.}$ Forma predeterminada de desenhar o objeto.
	2. $\textup{Semântica.}$ Define o que significa o elemento e com que objetivo ele deve ser utilizado.

### $\texttt{1.4.1. Visões de um Sistema.}$

1. Um sistema pode ser analisado por cinco visões interdependentes, estas são:
	1. *Visões de Casos de Uso:* Descreve o sistema do ponto de vista externo, isto é, as interações entre o sistema e os agentes externos ao sistema. Visão inicial do sistema.
	2. *Visão de Projeto:* Enfatiza características que oferecem suporte, tanto estrutural, quanto comportamental, às funcionalidades mais visíveis do sistema.
	3. *Visão de Implementação:* Gerenciamento de versões do sistema, construídas pelo agrupamento em módulos (componentes) e subsistemas.
	4. *Visão de Implantação:* Distribuição física do sistema em seus subsistemas e à conexão entre essas partes.
	5. *Visão do Processo:* Características de concorrência (paralelismo), sincronização e desempenho do sistema.
2. Podemos organizar as diferentes visões do sistema da seguinte forma:
![[Hierarquia de Visões do Projeto.png|450]]

