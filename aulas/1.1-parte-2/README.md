# Aula 1.1, Parte 2: As 33 etapas sem decorar: o que cada uma consome e produz

**No vídeo:** As 33 etapas do AI-DLC sem decorar: o que cada uma lê e grava

Vídeo da playlist "Curso de AI-DLC: desenvolvimento com agentes de IA, da ideia ao deploy", no canal MonogramaTech no YouTube.

## O que esta parte mostra

As 33 etapas do AI-DLC sem decorar: cada etapa tem um arquivo no repositório, e o cabeçalho dele é um cartão que diz quem faz, o que a etapa lê, o que ela grava e o que se confere no fim. Com o cartão e a mesma execução da Aula 0.2, em que um app de chamados de suporte foi do pedido ao deploy.

Nesta parte você vê:
- o cartão da Units Generation, campo por campo, e o que ela gravou nesta execução;
- o cartão da geração de código, com nove leituras e só duas obrigatórias;
- o jeito de não decorar a lista: seguir um arquivo de quem grava para quem lê, como os requisitos, lidos por nove etapas;
- as pontas: as etapas que não leem arquivo de outra etapa e os arquivos que nenhuma etapa lê;
- a checagem automática de citação: ela rodou 69 vezes nesta execução e falhou quatro, e o agente corrigiu cada caso;
- o que essa checagem confere (o nome do arquivo no texto) e o que fica com o revisor e com você.

Laboratório: aidlc-workflows v2.11.4 (commit 61fdb12) no Claude Code, com o Sonnet 5.5, em sete sessões de 18 a 20/11/2026; o repositório suporta outros harnesses, e o curso usa um, sem ranking. A AWS emulada é o LocalStack, na máquina do laboratório: medida de desempenho num emulador não vale como medida real. O app de chamados é um exemplo.

## Reproduza

Esta parte não tem bloco próprio: ela lê o repositório na versão 2.11.4 e a mesma execução do fio condutor da Aula 0.2. Os 33 cartões ficam no início de cada arquivo em core/aidlc-common/stages/, na tag v2.11.4 do repositório awslabs/aidlc-workflows: abra um e procure os campos consumes, produces e sensors. A instalação e a configuração do AI-DLC 2.11.4 estão testadas na descrição da Aula 0.1. Numa execução sua, a checagem de citação roda nas mesmas etapas, mas passa ou falha conforme o texto que o agente escrever. Rodar o agente consome o seu plano ou a sua API.

## Exercício

Uma etapa precisa de um arquivo que não existe. Quando você pode esperar isso, e quando é uma falha?

<details><summary>Uma boa resposta</summary>

A falta é normal quando a etapa que faz o arquivo não está no seu escopo. Aí ela trabalha com o que existe, sem inventar o arquivo. É uma falha quando o arquivo devia existir: por exemplo, porque você pulou a etapa que o faz. Aí o AI-DLC leva o caso a você. Você pode rodar a etapa que faz o arquivo ou pôr o arquivo no lugar. Nesta execução, algo parecido aconteceu na Unit da página. Uma etapa dela tinha as regras de negócio como leitura obrigatória, e o arquivo não existia. Para uma Unit de tela, o desenho funcional não grava as regras. O agente escreveu isso, com o nome do arquivo, e a checagem passou mesmo sem o arquivo existir.

</details>

## Fontes

- awslabs/aidlc-workflows v2.11.4 (commit 61fdb12, 13/11/2026): o cabeçalho dos 33 arquivos de core/aidlc-common/stages/, docs/guide/04-phases-and-stages.md, docs/guide/09-rules-and-the-learning-loop.md e docs/guide/glossary.md
- laboratório: Claude Code 2.1.327 a 2.1.330 com o Sonnet 5.5, sete sessões de 18 a 20/11/2026 (consultados em 21/11/2026)
