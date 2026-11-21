# Aula 0.2, Parte 1: Um pedido, cinco fases

**No vídeo:** Uma execução do AI-DLC do pedido ao deploy, em cinco fases

Vídeo da playlist "Curso de AI-DLC: desenvolvimento com agentes de IA, da ideia ao deploy", no canal MonogramaTech no YouTube.

## O que esta parte mostra

Uma execução inteira do AI-DLC, vista de cima: o mesmo pedido de uma linha da aula anterior, para um app de chamados de suporte, foi até o fim. Dois dias depois, o app rodava numa AWS emulada, com 29 etapas e 215 respostas da pessoa.

Nesta parte você vê:
- a fábrica que o próprio repositório descreve: o escopo é a linha de produção, a etapa é o posto, o agente é o trabalhador, e a saída aprovada é a ordem de serviço do posto seguinte; e não é cascata;
- a escolha do escopo feature, que passa pelas cinco fases;
- as cinco fases desta execução: Initialization, Ideation, Inception, Construction e Operation, com o que cada uma fez;
- onde a pessoa decidiu: as respostas, os pedidos de mudança, a aprovação do plano de cada Unit e os checkpoints;
- o que ficou no projeto: a pasta do intent, com os documentos e as respostas, e o código;
- o mapa do curso, módulo por módulo.

Laboratório: aidlc-workflows v2.11.4 (commit 61fdb12) no Claude Code, com o Sonnet 5.5, em sete sessões de 18 a 20/11/2026; o repositório suporta outros harnesses, e o curso usa um, sem ranking. A AWS emulada é o LocalStack, na máquina do laboratório: medida de desempenho num emulador não vale como medida real. O app de chamados é um exemplo.

## Reproduza

Esta parte não tem bloco próprio: a execução inteira levou sete sessões de condução. A instalação e a configuração do AI-DLC 2.11.4 estão testadas na descrição da Aula 0.1. O fio condutor se repete pelos mesmos passos, com a mesma estrutura de arquivos e as mesmas paradas para a sua decisão, mas não com o mesmo texto: o agente responde diferente a cada execução. Rodar o agente consome o seu plano ou a sua API.

## Exercício

Na Construction, falta um requisito. Você volta à Requirements Analysis para escrever o requisito que faltou. O que acontece com os postos depois dela?

<details><summary>Uma boa resposta</summary>

Cada saída aprovada é a ordem de serviço do posto seguinte. Por isso, esse posto e todos os seguintes voltam a ficar por fazer. Eles rodam de novo, em ordem. Os arquivos ficam no disco, e cada posto reaberto pergunta se você quer manter, mudar ou refazer o que já existe. Nesta execução, o agente perguntou no fim da Inception se devia reabrir os requisitos. A pessoa pediu só a atualização do arquivo, sem voltar àquele posto.

</details>

## Fontes

- awslabs/aidlc-workflows v2.11.4 (commit 61fdb12, 13/11/2026): AGENTS.md (What AI-DLC is), docs/guide/03-spaces-and-intents.md, docs/guide/04-phases-and-stages.md, docs/guide/05-scopes-and-depth.md, docs/guide/11-session-management.md, docs/guide/glossary.md e core/aidlc-common/stages/operation/feedback-optimization.md
- laboratório: Claude Code 2.1.327 a 2.1.330 com o Sonnet 5.5, sete sessões de 18 a 20/11/2026 (consultados em 21/11/2026)
