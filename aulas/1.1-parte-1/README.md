# Aula 1.1, Parte 1: As cinco fases e o que cada uma entrega

**No vídeo:** As cinco fases do AI-DLC e o que cada uma entrega

Vídeo da playlist "Curso de AI-DLC: desenvolvimento com agentes de IA, da ideia ao deploy", no canal MonogramaTech no YouTube.

## O que esta parte mostra

As cinco fases do AI-DLC, uma por uma: o que cada fase entrega à seguinte, quais das 33 etapas não têm condição e o que se confere na passagem de uma fase para outra. Tudo com os arquivos reais da mesma execução da Aula 0.2, em que um app de chamados de suporte foi do pedido ao deploy.

Nesta parte você vê:
- a diferença entre fase e etapa: as 33 etapas, três na Initialization, sete na Ideation, nove na Inception, sete na Construction e sete na Operation;
- sem condição ou condicional: só 11 etapas não têm condição, nenhuma delas na Operation, e o escopo decide quais etapas e fases entram;
- o que cada fase entrega, com os documentos desta execução: 17 na Ideation, 22 na Inception, 51 na Construction e 24 na Operation;
- o gate de verificação: as quatro coisas que ele confere na entrada da Inception, da Construction e da Operation, e as três checagens gravadas nesta execução;
- o caso do mvp, em que a passagem para a Inception fica sem checagem;
- o ciclo de retorno, que pode abrir um novo ciclo de Ideation.

Laboratório: aidlc-workflows v2.11.4 (commit 61fdb12) no Claude Code, com o Sonnet 5.5, em sete sessões de 18 a 20/11/2026; o repositório suporta outros harnesses, e o curso usa um, sem ranking. A AWS emulada é o LocalStack, na máquina do laboratório: medida de desempenho num emulador não vale como medida real. O app de chamados é um exemplo.

## Reproduza

Esta parte não tem bloco próprio: ela lê a mesma execução do fio condutor da Aula 0.2 e o repositório na versão 2.11.4. A instalação e a configuração do AI-DLC 2.11.4 estão testadas na descrição da Aula 0.1. O campo execution: de cada etapa fica no início de cada arquivo em core/aidlc-common/stages/, na tag v2.11.4 do repositório awslabs/aidlc-workflows. Uma execução sua passa pelas mesmas fases e etapas, com a mesma estrutura de arquivos e as mesmas paradas para a sua decisão, mas não com o mesmo texto: o agente responde diferente a cada execução. Rodar o agente consome o seu plano ou a sua API.

## Exercício

Em que fase nasce cada arquivo? O mapa das partes interessadas, o contrato das rotas, as regras de negócio e o roteiro de reversão.

<details><summary>Uma boa resposta</summary>

O mapa das partes interessadas nasce na Ideation, na primeira etapa, junto com a declaração da intenção. O contrato das rotas nasce na Inception, antes de qualquer código. As regras de negócio nascem na Construction, na primeira etapa de desenho da Unit. E o roteiro de reversão nasce na Operation, na etapa que monta a entrega automática, antes da etapa que implanta.

</details>

## Fontes

- awslabs/aidlc-workflows v2.11.4 (commit 61fdb12, 13/11/2026): docs/guide/04-phases-and-stages.md, docs/guide/05-scopes-and-depth.md, docs/guide/glossary.md, o campo execution: de core/aidlc-common/stages/*/*.md e core/aidlc-common/stages/operation/feedback-optimization.md
- laboratório: Claude Code 2.1.327 a 2.1.330 com o Sonnet 5.5, sete sessões de 18 a 20/11/2026 (consultados em 21/11/2026)
