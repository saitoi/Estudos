---
aliases:
  - requisitos
tags:
  - IMS
date: 2023-10-24
time: 15:50
complete:
---
# $\texttt{Requisitos.}$

- [i] Referência: Slide de [[Requisitos1.pdf|Requisitos I]], [[Requisitos2.pdf|Requisitos II]] e [[Requisitos3.pdf|Requisitos III]].

Antes de compreender o conceito de requisitos no desenvolvimento de um sistema, precisamos estabelecer do que se trata a engenharia de requisitos.

1. $\textup{Engenharia de Requisitos.}$ Processo de estabelecer os serviços que o cliente requer de um sistema e as restrições sob as quais ele opera e é desenvolvido.

Nesse sentido, os requisitos de um sistema compõem as descrições dos serviços do sistema e restrições que são gerados durante o processo da Engenharia de Requisitos.

Os requisitos possuem duas funções principais.

1. Como são base para a licitação de um contrato, eles devem estar aberto a interpretação. Isso implica que os requisitos devem ser definidos de forma **abstrata** sem solução pré-definida.
2. Os requisitos devem ser definidos de forma detalhada, uma vez que o que está fora da **documentação** também está fora do escopo. Caso o contrato seja concedido, o contratante deve escrever uma **definição de sistema** com mais detalhes para a validação do mesmo.

Existem dois tipos de requisitos (nível de abstração) que serão descritos abaixo.

1. **Requisitos do usuário.** Declaração em linguagem natural mais diagramas de serviço que o sistema fornece e suas restrições operacionais. Normalmente, é desenvolvido para clientes (usuários finais, gerentes, etc.).
2. **Requisitos do sistema.** Documento estruturado contendo as descrições detalhadas das funções, serviços e restrições operacionais do sistema. Sendo direcionado para os clientes e desenvolvedores de software.

As partes interessadas do sistema ou também conhecidas como **stakeholders** corresponde a qualquer pessoa ou organização afetada pelo sistema, isto é, que tenha algum interesse legítimo. Aqui estão alguns exemplos:

- Usuários finais.
- Gerentes do sistema.
- Proprietários do sistema.
- Partes interessadas externas.

Podemos subdividir os requisitos em duas categorias: Requisitos funcionais e não-funcionais.

1. **Requisitos funcionais (RF).** Descrevem em detalhes as funcionalidades ou serviços que o sistema deve oferecer, como o sistema deve reagir a entradas específicas e como o sistema deve se comportar em situações específicas. Essas declarações são em alto-nível, ou seja, abstratas.
3. **Requisitos não-Funcionais (RNF).** Restrições nos serviços ou funções oferecidas pelo sistema aplicáveis ao sistema como um todo no lugar de recursos/serviços individuais. Isso inclui as propriedades do sistema como confiabilidade, tempo de resposta ou também restrições como linguagem de programação. Aqui estão alguns tipos de requisitos não-funcionais:
	1. **Requisitos do produto.** Especificam que o produto deve se comportar de uma maneira particular, por ex. velocidade de execução, restrição de armazenamento.
	2. **Requisitos organizacionais.** São consequência de políticas e procedimentos organizacionais, tal como padrões de processos usados, requisitos de implementação, etc.
	3. **Requisitos externos.** Surgem de fatores externos ao sistema e seu desenvolvimento, por exemplo requisitos legislativos.

Aqui estão exemplos de métricas para RNFs.

![[MetricasRequisitos.png|650]]

Dentre os processos da Engenharia de Requisitos, podemos estipular um conjunto mínimo de atividades comuns a todos os processos:

1. Levantamento de requisitos.
2. Análise de requisitos.
3. Validação de requisitos.
4. Gerenciamento de requisitos.

Aqui está uma descrição detalhada de cada um dos processos da engenharia de requisitos.

1. **Elicitação de Requisitos.** Também conhecida como **definição de requisitos**, essa etapa envolve a colaboração entre a equipe técnica e os clientes (partes interessadas/**stakeholders**) para compreender o escopo do aplicativo, os serviços a serem oferecidos e as limitações operacionais do sistema. As principais fases da elicitação de requisitos incluem:
	1. **Descoberta de requisitos.** Consiste na interação com as partes interessadas para descobrir os requisitos.
	2. **Classificação e organização de requisitos.** Agrupamento dos requisitos de forma coerente, organizando-os em conjuntos.
	3. **Priorização e negociação de requisitos.** Priorizar e resolver conflitos com relação aos requisitos.
	4. **Especificação de requisitos.** Requisitos são documentados detalhadamente e passam para a próxima etapa.
2. 