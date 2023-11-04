---
aliases:
  - ims_livro
tags:
  - IMS
date: 2023-10-10
time: 15:27
complete: false
---
# Anotações Livro

Capítulos relevantes:

- [x] Capítulo 1 (Edição nova)
- [x] Capítulo 4 - seção 4.1 até 4.3 (Edição nova)
- [x] Capítulo 5 - seção 5.1 até 5.3 (Edição nova e antiga)
- [ ] Capítulo 5 - seção 5.4 (Edição nova)
- [ ] Capítulo 8 - seção 8.4
- [x] Capítulo 9 - seção 9.1 até 9.7 (Edição antiga)
- [i] Retornar às seções abaixo para inserir os exemplos.

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

### $\texttt{1.4.2. Diagramas da UML.}$

1. $\textup{Artefatos de software.}$ Documentos tanto $\textit{textuais}$ quanto $\textit{gráficos}$ criados quando utilizamos a linguagem UML como linguagem de suporte à modelagem. Também são conhecidos por simplesmente $\textit{artefatos}$.
2. Os artefatos gráficos podem ser definidos pela utilização de diagramas da UML.
3. Os retângulos com setas apontando para ele representam agrupamentos (tipos) enquanto os retângulos com setas apenas saindo dele são os diagramas propriamente ditos:

![[diagramasUML.png|750]]

# $\texttt{4.0. Modelagem de Casos de Uso.}$

1. Os modelos de casos de uso representam os possíveis usos do sistema segundo um observador externo.
2. A construção do modelo envolve a definição de inúmeros componentes: $\textit{casos de uso}$, $\textit{atores}$ e $\textit{relacionamentos}$.

## $\texttt{4.1. Modelos de Casos de Uso.}$

1. O MCU representa os possíveis usos de um sistema por um observador externo a ele.
2. Cada um dos usos está relacionado a um ou mais requisitos funcionais identificados para o sistema.
3. Esse modelo envolve alguns componentes centrais tal como os próprios $\textit{casos de uso}$, $\textit{atores}$ e $\textit{relacionamentos}$.

### $\texttt{4.1.1. Casos de Uso.}$

1. Por definição, um $\textit{caso de uso}$ se trata da especificação de uma sequência completa de interações entre um sistema e um ou mais agentes externos ao sistema.
2. Representa um relato externo das funcionalidades do sistema, *sem revelar a estrutura e seus comportamentos internos*.
3. Os casos de uso são descritos de forma textual e não são definidos pelo padrão UML, havendo, portanto, diversos estilos de descrição possíveis.
4. As três dimensões em que o estilo de descrição pode variar são: *grau de detalhamento*, *grau de abstração* e o *formato*.

#### $\texttt{4.1.1.1. Formato.}$

1. Formato está relacionado à organização da narrativa textual e correspondem a três tipos mais conhecidos de formatos: $\textit{contínuo}$, $\textit{numerado}$ e o $\textit{tabular}$.

#### $\texttt{4.1.1.2. Grau de Detalhamento.}$

1. O grau de detalhamento pode variar de $\textit{sucinto}$ até a descrição com vários detalhes ($\textit{expandido}$).

#### $\texttt{4.1.1.3. Grau de Abstração.}$

1. Diz respeito à existência ou não de menção a aspectos relativos à tecnologia durante a descrição desse caso de uso, podendo ser dividido em: $\textit{real}$ ou $\textit{essencial}$.

#### $\texttt{4.1.1.4. Cenários.}$

1. $\textup{Cenário.}$ Descrição de uma das maneiras pelas quais um caso de uso pode ser utilizado. Podendo haver, normalmente, diversos cenários para um mesmo caso de uso.
2. $\textup{Realização de um caso de uso.}$ Conjunto de diagramas e artefatos textuais que especificam como esse caso de uso é executado internamente ao sistema em desenvolvimento.

### $\texttt{4.1.2. Atores.}$

1. $\textup{Ator.}$ Elemento $\textit{externo}$ ao sistema que $\textit{interage}$ com o mesmo.
2. Atores de um sistema podem ser agrupados em algumas categorias, tal como:
	1. $\textit{Cargos.}$ (p. ex., Empregado, Cliente, Gerente etc.).
	2. $\textit{Organizações ou divisões de uma organização.}$ (p. ex., Empresa Fornecedora, Agência de Impostos etc.).
	3. $\textit{Outros sistemas de software}$. (p. ex., Sistema de Cobrança, Sistema de Estoque de Produtos etc.).
	4. $\textit{Equipamentos}$ com os quais o sistema deve se comunicar (p. ex., Leitora de Código de Barras Sensor etc.).
3. Um ator corresponde a um $\textit{papel}$ representado em relação ao sistema e, portanto, é importante que o nome dado ao ator lembre o papel que ele representa.
4. Atores são subdivididos em duas categorias:
	1. $\textup{Atores primários.}$ Inicia a sequência de interações de um caso de uso, ou seja, corresponde aos agentes externos para os quais o sistema produz benefícios direto.
	2. $\textup{Atores secundários.}$ Responsáveis por supervisionar, operar, manter ou auxiliar na utilização do sistema pelos atores primários.

### $\texttt{4.1.3. Relacionamentos.}$

1. Relacionamentos possuem a função de relacionar atores e casos de uso, podendo até estarem associados entre si.
2. A UML define os seguintes relacionamentos para os modelos de casos de uso, cada um com sua notação gráfica:
	1. $\textit{Comunicação}$.
	2. $\textit{Inclusão}$.
	3. $\textit{Extensão}$.
	4. $\textit{Generalização}$.

### $\texttt{4.1.3.1. Relacionamento de Comunicação.}$

1. Informa a que caso de uso o ator está associado de modo que este (ator) interage (troca informações) com o sistema com relação à aquele caso.

### $\texttt{4.1.3.2. Relacionamento de Inclusão.}$

1. Relacionamento exclusivo entre casos de uso usado para se referir a um comportamento padrão entre diferentes casos de uso semelhante à ideia de chamarmos uma função repetidas vezes.
2. $\textup{Caso de uso inclusor}$. Caso de uso que inclui o comportamento de outro caso de uso.
3. $\textup{Caso de uso incluso}$. Caso de uso cujo comportamento é incluído por outros.
4. A sintaxe padrão para a inclusão de um caso de uso é *Include (nome do caso de uso incluso)*.

### $\texttt{4.1.3.3. Relacionamento de Extensão.}$

1. Dados dois casos de uso $\text{A}$ e $\text{B}$, caso um ou mais cenários de $\text{B}$ incluírem o comportamento de $\text{A}$ dizemos que existe um relacionamento de extensão entre eles.
2. Por esse viés, diz-se que $\text{A}\textit{ estende }\text{B}$ e $\text{B}$ é chamado de $\textit{estendido}$ enquanto $\text{A}$ se refere ao $\textit{extensor}$.
3. Vale ressaltar que a existência do caso de uso estendido dever ser $\textit{independente}$ da existência de quaisquer casos de uso que estendam o primeiro.
- [i] Considere o caso de uso $\textup{Editar Documento}$, que descreve a sequência de interações quando o usuário edita um documento. Em um cenário usual, o ator abre o documento, modifica-o, salva as modificações e fecha o documento. No entanto, existe a possibilidade do ator desejar que o sistema realize alguma correção ortográfica ou substituição de texto. Para isso, chamaremos os casos de uso $\textup{Corrigir Ortografia}$ e $\textup{Substituir Texto}$.

### $\texttt{4.1.3.4. Relacionamentos de Generalização.}$

1. Existente entre dois casos de uso ou dois atores de modo que um deles herde características de outro, mais genérico, este último sendo normalmente chamado de caso de uso (ator) $\textit{base}$. O caso de uso (ator) $\textit{herdeiro}$ pode especializar o comportamento do caso de uso (ator) base ou redefini-lo.
2. As sequências de comportamento descritas no caso de uso mais genérico são reutilizadas pelos casos de uso herdeiros e podemos especificar quais passos do caso de uso pai estão sendo redefinidos pelo primeiro por meio do posicionamento de marcadores.
3. O caso de uso genérico pode ser $\textit{concreto}$ ou $\textit{abstrato}$.
	1. Um caso de uso abstrato não possui comportamento associado a ele (o mais recomendado).
	2. Um caso de uso concreto possui algum comportamento associado.
4. *Generalização entre atores* significa que o ator herdeiro possui o mesmo comportamento (em relação ao sistema) que o ator do qual ele herda. Com efeito, se o sistema identifica um ator $\text{A}$, então todos os casos de uso associados a $\text{A}$ identificam os atores herdeiros também como $\text{A}$.
5. Propriedade da generalização: Os casos de uso válidos para o ator herdeiro não são válidos para o ator pai.
- [i] Suponha uma biblioteca com dois tipos de usuários: Alunos e professores. Os dois tipos de usuários possuem o mesmo comportamento de realizar empréstimos e reservas de livros. No entanto, o professor possui uma funcionalidade a mais, isto é, ele pode requisitar a compra de títulos de livros à biblioteca. Nesse caso, podemos definir um ator Usuário e outro Professor de modo que Professor herde o Usuário, mas ele também interage com a requisição de compra de novos títulos de livros.

### $\texttt{4.1.3.5. Quando usar Relacionamentos no MCU.}$

1. Quando usar cada um dos relacionamentos abordados acima:
	1. $\textbf{Inclusão}$. Quando o mesmo comportamento se repetir em mais de um caso de uso. Desse modo, o comportamento comum será refatorado como o <ins>caso de uso incluso</ins> e estará $\textit{necessariamente}$ contido em todos os cenários dos <ins>casos de inclusores</ins>.
	2. $\textbf{Extensão}$. Quando um comportamento $\textit{eventual}$ de um caso de uso tiver de ser descrito. Ou também quando se deseja estender o comportamento preexistente sem modificar sua descrição original.
	3. $\textbf{Generalização entre casos de uso}$. Identificar dois ou mais casos de uso com comportamentos semelhantes. Crie um caso de uso mais genérico (abstrato) e o relacione por generalização aos casos de uso semelhantes.
	4. $\textbf{Generalização entre atores}$. Quando precisar definir um ator que desempenhe um papel que já é desempenhado por outro em relação sistema, mas que possui algum comportamento particular adicional.

### $\texttt{4.1.3.6. Decomposição Funcional e Relacionamentos entre Casos de Uso.}$

*Não é tão importante assim pelo pouco que eu vi..*

## $\texttt{4.2. Diagrama de Casos de Uso.}$

1. Nessa seção, nos interessa a perspectiva gráfica do MCU, representada por meio dos diagramas de casos de uso (DCU).
2. Esse diagrama representa $\textit{graficamente}$ os atores, casos de uso e relacionamentos entre elementos.
3. Os atores são representados pela figura de um boneco, com o nome do ator definido abaixo. <ins>Embora os atores nem sempre correspondam a seres humanos</ins>.
4. Cada caso de uso é representado por uma elipse de modo que o nome do caso de uso é representado abaixo ou no interior dessa elipse.
5. Um relacionamento de comunicação é representado por um segmento de reta ligando o ator ao caso de uso, podendo ter ou não um sentido para denotar o iniciante da sequência de interações. Aqui está uma breve representação:

 ![[diagramaDeCasoDeUso.png|480]]

6. Podemos representar a fronteira em um diagrama de caso de uso por meio de um retângulo em que os casos de uso se encontram em seu interior, tal como abaixo:

![[diagramaDeCasoDeUso2.png|600]]

7. $\textup{Fronteiras}$. *Definição de fronteiras bem aqui..*
8. O relacionamento de inclusão em que um caso de uso $\text{A}$ inclui um caso de uso $\text{B}$ é representado por um seta direcionada e tracejada de $\text{A}$ para $\text{B}$. Ela é rotulada com o estereótipo predefinido $\textup{include}$, tal como no exemplo abaixo.

![[diagramaDeCasoDeUso3.png|650]]

9. O relacionamento de extensão é representado da mesma forma que o anterior (relacionamento de inclusão), porém é rotulado pelo estereótipo predefinido $\textup{extend}$.
10. Portanto, se um caso de uso $\text{A}$ estende o $\text{B}$, teremos uma seta tracejada e direcionada de $\text{A}$ para $\text{B}$ da seguinte forma:

![[diagramaDeCasoDeUso4.png|650]]

11. O relacionamento de generalização se encontra abaixo tanto entre atores distintos e casos de uso também.

![[diagramaDeCasoDeUso5.png|770]]

## $\texttt{4.3. Identificação dos Elementos do MCU.}$

1. Essa seção trata de algumas técnicas que podem ser aplicadas para a correta identificação dos elementos de um MCU.
2. Os atores e os casos de uso referentes ao sistema são identificados na fase de levantamento de requisitos.

### $\texttt{4.3.1. Identificação de Atores.}$

1. O analista de sistemas deve identificar quais as fontes de informações a serem processadas e quais são os destinos das informações geradas pelo sistema.
2. Aqui estão algumas perguntas úteis na etapa de identificação dos atores:
	1. Que órgãos, empresas ou pessoas utilizarão o sistema?
	2. Que sistemas ou equipamentos irão se comunicar com o sistema?
	3. Alguém deve ser informado de alguma ocorrência do sistema?
	4. Quem está interessado em certo requisito funcional do sistema?

### $\texttt{4.3.2. Identificação de Casos de Uso.}$

1. Podemos distinguir entre dois tipos de casos de uso, isto é, $\textit{primários}$ e $\textit{secundários}$.

#### $\texttt{4.3.2.1. Casos de Uso Primários.}$

1. Casos de uso primários representam os $\textit{objetivos}$ dos atores.
2. Aqui estão algumas perguntas a serem feitas para facilitar a identificação desses casos de uso:
	1. Quais são as necessidades e os objetivos de cada ator em relação ao sistema?
	2. Que informações o sistema deve produzir?
	3. O sistema deve realizar alguma ação que ocorre regularmente no tempo?
	4. Para cada requisito funcional, existe um (ou mais) caso(s) de uso para atendê-lo?
3. Aqui estão algumas outras formas de identificar casos de uso:
	1. $\textit{Caso de uso }$$\textquotedblleft$$\textit{oposto}$$\textquotedblright\textit{:}$ Caso de uso cuja realização desfaz o resultado da realização de outro.
	2. $\textit{Caso de uso que precede outro caso de uso:}$ Algumas vezes certas condições devem ser verdadeiras antes da execução de um caso de uso.
	3. $\textit{Caso de uso que sucede a outro caso de uso:}$ Deve-se pensar nas consequências da realização de um caso de uso.
	4. $\textit{Caso de uso temporal:}$ Pode haver funcionalidades do sistema que não estejam atreladas a um ator, ou seja, ocorrem de tempos em tempos tal como a geração de um relatório.
	5. $\textit{Caso de uso relacionado a alguma condição interna:}$ Não está relacionado a algum ator diretamente.

#### $\texttt{4.3.2.2. Casos de Uso Secundários.}$

1. São aqueles casos de uso que não trazem benefícios diretos para os atores, mas são necessários para o funcionamento adequado do sistema. Aqui estão alguns exemplos:
	1. $\textit{Manutenção de Cadastros.}$
	2. $\textit{Manutenção de usuários e perfis.}$
	3. $\textit{Manutenção de informações provenientes de outros sistemas.}$

# $\texttt{5.0. Modelagem de Classes do Domínio.}$

1. As funcionalidades externas e visíveis do sistema é possibilitada por meio da colaboração entre objetos internos. Essa colaboração pode ser vista sob duas perspectivas, isto é, o $\textit{aspecto dinâmico}$ e o $\textit{aspecto estrutural estático}$.
2. O aspecto dinâmico descreve a troca de mensagens entre os objetos e sua reação a eventos que ocorrem no sistema.
3. Por outro lado, o aspecto estrutural estático da cooperação permite entender a estrutura interna do sistema para que as funcionalidades externas sejam produzidas.
4. É dito $\textit{estático}$ por que não apresenta a interação dos objetos ao longo do tempo e $\textit{estrutural}$ porque a estrutura das classes de objetos e as relações entre elas são representadas.
5. O $\textit{diagrama de objetos}$ será apresentado nas seções abaixo.

## $\texttt{5.1. Modelo de Classes.}$

1. Considerando a evolução do modelo de classes, há três níveis de abstração que o modelo de classes passa:
	1. $\textit{Modelo de classes do domínio}$. Representa as classes do domínio do negócio em questão, sendo construído na fase de análise.
	2. $\textit{Modelo de classes de especificação}$. Extensão do modelo de classes de domínio por meio da adição de detalhes específicos conforme a solução do software for escolhida.
	3. $\textit{Modelo de classes de implementação}$. Extensão do modelo de classes de especificação que corresponde à implementação das classes em alguma linguagem de programação, normalmente uma linguagem orientada a objetos.

## $\texttt{5.2. Nomenclatura utilizada.}$

1. Para identificadores, quaisquer espaços em brancos e preposições do nome são removidos.
2. Para nomes de classes e nomes de relacionamentos, as palavras componentes do nome são escritas começando com letra maiúscula.
3. Para nomes de atributos e nomes de operações deve-se escrever a primeira palavra do nome em minúscula e as palavras subsequentes em maiúscula.

## $\texttt{5.3. Diagrama de Classes.}$

1. O diagrama de classes é usado na construção do modelo de classes desde o nível de análise até o nível de especificação, sendo o diagrama mais rico em notação dentre os diagramas da UML.

### $\texttt{5.3.1. Classes.}$

1. Classes são representadas por caixas com no máximo três compartimentos exibidos.
2. O primeiro compartimento contém o nome da classe, no segundo são declarados os atributos e, finalmente, no terceiro temos as ações que um objeto sabe realizar.
3. Estruturalmente, as classes são compostas de $\textit{atributos}$ e $\textit{operações}$. A cada atributo, está associado um conjunto de valores que esse atributo pode assumir. Por outro lado, as operações correspondem à descrição das ações que os objetos de uma classe sabem realizar.

![[DiagramaDeClasse.png]]

### $\texttt{5.2.2. Associações.}$

1. Dada uma classe podemos criar um objeto ou instância dela. Desse modo, os objetos podem se relacionar uns com os outros por meio de $\textit{associações}$ para possibilitar a troca de mensagens produzir as funcionalidades do sistema.
2. Uma associação é representada por uma linha ligando as classes às quais pertencem os objetos relacionados.
3. Algumas das características mais importantes da associações incluem multiplicidade, nome, direção de leitura, papéis, tipo de participação e conectividade.

#### $\texttt{5.2.2.1. Multiplicidades.}$

1. As associações permitem a representação da informação dos limites inferior e superior da *quantidade de objetos* aos quais outro objeto pode estar associado, esses limites são denominados de $\textit{multiplicidade}$.
2. Podemos ter símbolos distintos representando o mesmo conceito, por exemplo, o símbolo $\textquotedblleft$$1$$\textquotedblright$ é equivalente à utilização do $\textquotedblleft$$1..1$$\textquotedblright$, tal como $\textquotedblleft$$*$$\textquotedblright$ equivale a $\textquotedblleft$$0..*$$\textquotedblright$. Aqui está uma tabela contendo todas as simbologias:

| Símbolo | Significado              |
| ------- | ------------------------ |
| 0…1     | Uma instância opcional   |
| 1       | Exatamente uma instância |
| 0…*     | Zero ou mais instâncias  |
| 1…*     | Pelo menos uma instância |

3. Há uma representação adicional para indicar um intervalo específico que corresponde a $1_{i}..1_{s}$.
- [i] Suponha duas classes $\textup{Pedido}$ e $\textup{Cliente}$ juntamente de uma associação entre elas. Como sabemos que um cliente pode estar associado a nenhum ou a alguns pedidos distintos poderíamos usar o $\textquotedblleft$$1$$\textquotedblright$ saindo de $\textup{Cliente}$ e chegando em $\textquotedblleft$$0..*$$\textquotedblright$, ou seja, para um cliente temos nenhum ou mais pedidos:

![[DiagramaDeClasse3.png|600]]

4. O * denota que não há um limite superior predefinido para a quantidade máxima de objetos.
5. $\textup{Conectividade}$. Tipo de associação entre duas classes sendo definida pela multiplicidade.

| Conectividade      | Multiplicidade de um extremo | Multiplicidade de outro extremo |
| ------------------ | ---------------------------- | ------------------------------- |
| Um para um         | 0…1                          | 0…1                             |
| Um para muitos     | 0…1                          | \* ou 1…\* ou _…_ \*            |
| Muitos para muitos | \* ou 1…\* ou _…_            | \* ou 1…\* ou _…_ \*            |

#### $\texttt{5.2.2.2. Participações.}$

1. Está relacionada à necessidade ou não da existência de uma associação entre objetos, podendo ser $\textit{obrigatória}$ ou $\textit{opcional}$.
2. Se o valor mínimo da associação é igual a 1, significa que a participação é obrigatória, caso contrário a participação é opcional.

![[diagramaDeClasse4.png|700]]

- [i] Considerando a primeira relação da tabela acima, podemos concluir que a participação do $\textup{Departamento}$ é obrigatória e, por outro lado, a participação da classe $\textup{Empregado}$ é parcial (pode haver empregados que não estejam associados a um departamento).

#### $\texttt{5.2.2.3. Nome da Associação, Direção de Leitura e Papéis.}$

1. Esses recursos empregados para facilitar a compreensão de uma associação segundo a UML.
2. O *nome da associação* é posicionado na linha de associação, a meio caminho das classes envolvidas.
3. A direção de leitura indica como a associação deve ser lida, sendo indicada por um pequeno triângulo posicionado ao lado do nome da associação.
4. Uma característica complementar à utilização de nomes é a atribuição de papéis relacionados à associação.

#### $\texttt{5.2.2.4. Classes Associativas.}$

1. Classes associativas são classes que estão ligadas a associações ao invés de estarem ligadas a outras classes.
2. Normalmente ocorre quando duas ou mais classes estão associadas e é necessário manter informações referentes a essa associação.
3. Uma classe associativa é representada pela mesma notação que as outras classes, no entanto está ligada por uma linha tracejada a uma associação.
4. Nesse caso não é necessário nomear a linha de associação de uma classe associativa, pois a classe de associação é o suficiente para exprimir o significado desejado.

#### $\texttt{5.2.2.5. Associações Ternárias.}$

1. Associações ternárias são necessárias para associar objetos de três classes distintas, tal como na figura abaixo.

![[diagramaDeClasse5.png|700]]

2. Por fim, podemos encaixar o conceito de classe associativa e de associação interna, onde existe uma classe associativa ternária ligada a uma associação ternária.

![[diagramaDeClasse6.png|700]]

#### $\texttt{5.2.2.6. Associações Reflexivas.}$

1. Associações reflexivas ou $\textit{autoassociações}$ ligam objetos da mesma classe.
2. No entanto, cada objeto possui um papel distinto nessa associação, tal como na autoassociação ilustrada abaixo.

![[diagramaDeClasse7.png|550]]

#### $\texttt{5.2.2.7. Agregações e Composições.}$

1. À toda associação podemos atrelar uma $\textit{semântica}$ (significado).
2. Um dos significados que uma associação pode ter está relacionado a relações $\textit{todo-parte}$ existente entre dois objetos e na qual um objeto $\textit{está contido}$ no outro e outro $\textit{contém}$ esse objeto.
3. A UML define dois tipos de relacionamentos $\textit{todo-parte}$, a $\textit{agregação}$ e a $\textit{composição}$.
4. Diferenciais das agregações e composições com relação à associação:
	1. Agregações/composições são assimétricas, ou seja, se um objeto A é parte de um objeto B, o objeto B não pode ser parte do objeto A.
	2. Agregações/composições propagam comportamento, se um comportamento se aplica a um todo então ele também se aplica a cada uma das partes.
	3. Nas agregações/composições, as partes são normalmente criadas e destruídas pelo todo.
5. Para identificar a necessidade de se utilizar uma agregação ou composição podemos fazer as seguintes perguntas, mas antes considere duas classes $\text{X}$ e $\text{Y}$. Se uma delas for sim então provavelmente teremos um relacionamento todo-parte entre $\text{X}$ e $\text{Y}$.
	1. *$\text{X}$ tem um ou mais $\text{Y}$?*
	2. *$\text{Y}$ é parte de $\text{X}$?*
6. Graficamente podemos representar a agregação por um losango situado na ponta da associação e ligado à classe que representa o todo, enquanto a composição é indicada por um losango preenchido.
7. Diferenças entre agregação e composição:
	1. Na agregação, a destruição de um objeto todo não implica na destruição do objeto parte.
	2. Na composição, os objetos parte pertencem a um único todo

*Tem mais coisa por aqui mas não é necessária..*

# $\texttt{8.0. Especificação de Classes, Propriedades e Associações.}$

*Colocar coisas aqui..*

## $\texttt{8.4. Especificação de Associações.}$



# $\texttt{9.0. Generalização}$

1. Podemos também representar relacionamentos entre classes ao invés de objetos, denotando relações de generalidade e especificidade entre as classes envolvidas.
2. Por exemplo, o conceito de $\textit{mamífero}$ é mais genérico que o conceito $\textit{ser humano}$ e, portanto, podemos chamar esse relacionamento de *relacionamento de generalização* ou *de especialização*.

## $\texttt{9.1. Introdução.}$

1. Para compreender o conceito de generalização, usaremos o exemplo abaixo.
- [i] Considere duas classes, uma de $\textup{Funcionário}$ que contém os atributos *nome, endereço, númeroMatrícula e salárioBase*. No entanto, existe um tipo especial de funcionário os $\textup{Vendedores}$ que possuem todos os atributos dos funcionários mais alguns específicos. Desse modo, podemos dizer que a classe de vendedores $\textit{herda}$ propriedades da classe de funcionários.

### $\texttt{9.1.1. Terminologia.}$

1. O termo $\textit{subclasse}$ é usado para se referir à classe que herda as propriedades de outra classe por meio da generalização.
2. Temos também a $\textit{superclasse}$ que possui propriedades que estão sendo herdadas por outra classe.

*Outras terminologias não tão importantes assim..*

### $\texttt{9.1.2. Generalização X Associação.}$

1. A principal diferença entre uma generalização e uma associação está no fato de que a generalização é estabelecida entre classes enquanto a associação é apenas entre objetos.
2. Representamos as generalizações da seguinte forma.

![[diagramaDeClasse8.png|800]]

### $\texttt{9.1.3. Herança de Associações.}$

1. Ao se estabelecer uma associação, as subclasses de uma das associações são herdadas para a outra associação.
*Inserir exemplo bem aqui..*

## $\texttt{9.2. Hierarquias de generalização.}$

1. A generalização pode ser aplicada a diferentes níveis, ou seja, uma subclasse pode também ser uma superclasse de outra.

### $\texttt{9.2.1. Transitividade.}$

1. Uma das características importantes da hierarquia de generalização é a $\textit{transitividade}$, isto é, uma classe em uma hierarquia herda tanto as propriedades da superclasse diretamente acima dela quanto das superclasses não imediatas (acima dessa).
- [i] Suponha uma hierarquia de generalização de três níveis em que temos a classe $\textup{Vendedor}$ que herda atributos de $\textup{Empregado}$ que, por sua vez, herda propriedades de $\textup{Pessoa}$.

![[Generalização.png|500]]

### $\texttt{9.2.2. Assimetria.}$

1. Uma propriedade importante da generalização é a assimetria, isto é, se uma classe $\text{A}$ for uma generalização de uma classe $\text{B}$, então $\text{B}$ não pode ser uma generalização de $\text{A}$.

## $\texttt{9.3. Herança Múltipla.}$

1. Uma classe pode ter mais de uma superclasse e denominamos isso de *herança múltipla*.
- [i] O diagrama abaixo representa um carro anfíbio que possui tanto características de um carro quanto de um anfíbio.

![[Generalização2.png|600]]

## $\texttt{9.4. Classes Abstratas.}$

1. A possibilidade de se gerar instâncias de uma classe provém da existência de classes $\textit{concreta}$. No entanto, podemos ter classes que não geram instâncias diretamente, estas são as $\textit{classes abstratas}$.
2. Essas classes só existem em hierarquias de generalização e facilitam a organização da mesma.
3. Na UML, as classes abstratas são representadas por seu nome em $\textit{itálico}$ tal como na figura abaixo.

 

## $\texttt{9.5. Definição de Restrições sobre uma Generalização.}$

1. As restrições predefinidas da UML para tratar de generalizações pode ser encontrada na tabela abaixo.

| Restrição  | Significado                                                                                          |
| ---------- | ---------------------------------------------------------------------------------------------------- |
| sobreposta | Posteriormente, podem ser criadas subclasses que herdem de mais de uma subclasse (herança múltipla). |
| disjunta   | Quaisquer subclasses criadas posteriormente poderão herdar de somente uma subclasse.                 |
| completa   | Todas as subclasses possíveis foram enumeradas na hierarquia.                                        |
| incompleta | Nem todas as subclasses foram enumeradas na hierarquia.                                              |

2. Vale notar que as duas primeiras restrições e as duas últimas são exclusivas entre si, ou seja, não faz sentido definir subclasses sobrepostas e disjuntas ou completas e incompletas.
- [i] Aqui está um exemplo da utilização da restrição $\textup{incompleta}$ para a superclasse $\textup{Veículo}$ com o intuito de informar que há outras subclasses de $\textup{Veículo}$ que não estão sendo representadas.

![[Generalização5.png|500]]

- [i] Aqui está um exemplo da utilização das restrições $\textup{completa}$ e $\textup{disjunta}$ na superclasse $\textup{Indivíduo}$ e suas superclasses $\textup{Homem}$ e $\textup{Mulher}$. Nesse caso, $\textup{disjunta}$ nos informa que não há objeto na hierarquia que seja tanto homem quanto mulher.

![[Generalização6.png|550]]

## $\texttt{9.6. Refinando o Modelo de Classes com Generalização.}$

1.  Podemos refinar o modelo de classes por meio de duas técnicas alternativas e complementares: $\textit{Generalização}$ e $\textit{especialização}$.
2. Caso identificarmos duas classes semelhantes, podemos criar uma generalização, ou seja, uma classe mais genérica e definir as classes anteriores como subclasses dessa recém-criada.
3. Podemos também aplicar a especialização com o intuito de criar classes mais específicas a partir de uma classe preexistente, normalmente quando foi descoberta uma propriedade que justifique a criação de uma nova classe.

## $\texttt{9.7. Herança de Operações e Polimorfismo.}$

1. Uma subclasse herda as propriedades da subclasse que tenham visibilidade pública ou protegida.
2. Caso algum comportamento da subclasse for diferente, talvez será necessário redefinir o comportamento dessa operação.

### $\texttt{9.7.1. Operações Polimórficas.}$

1. Operações polimórficas são operações de mesma assinatura definidas em diferentes níveis da hierarquia de generalização e que possuem comportamento distinto.
2. Nesse viés, é implementado o *princípio do polimorfismo* no qual duas ou mais classes respondem à mesma mensagem de forma diferente.

### $\texttt{9.7.2. Operações Abstratas e Polimorfismo.}$

1. Em termos de operações, uma classe é dita abstrata quando ela possui pelo menos uma *operação abstrata*.
2. Uma operação é dita abstrata quando ela não possui implementação.
3. As subclasses que herdam dessa superclasse abstrata devem fornecer uma implementação para a operação, caso contrário elas também serão abstratas.

