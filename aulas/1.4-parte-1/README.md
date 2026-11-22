# Aula 1.4, Parte 1: Gates, aprovação e o que o agente nunca decide sozinho

**No vídeo:** Quem decide no AI-DLC: gates, pedidos de mudança e o que fica com você

Vídeo da playlist "Curso de AI-DLC: desenvolvimento com agentes de IA, da ideia ao deploy", no canal MonogramaTech no YouTube.

## O que esta parte mostra

No gate do plano de entrega, a pessoa escolheu pedir mudança, e o agente perguntou de volta: o que deve mudar? Nove minutos e três revisões depois, ela aprovou. Esta parte mostra cada passo e o que o AI-DLC nunca decide sozinho.

Nesta parte você vê:
- o gate de aprovação: as duas saídas, a próxima etapa calculada pelo motor e a resposta em palavras suas;
- por que só uma mensagem sua fecha o gate (165 turnos humanos nesta execução);
- um pedido de mudança real: revisão 1, 2 e 3, a saída aceitar como está e o agente perguntando em vez de adivinhar;
- os três jeitos de responder às perguntas de uma etapa: guiado, editando o arquivo ou conversando;
- o que continua com você na Construction, com ou sem autonomia: o plano de código, a verificação, o esqueleto e as falhas;
- o que nenhum ajuste tira de você, e para que servem as guardas.

11.4 (commit 61fdb12) no Claude Code, com o Sonnet 5.5, na execução da Aula 0.2 (sete sessões de 18 a 20/11/2026); o repositório suporta outros harnesses, e o curso usa um, sem ranking. O app de chamados é um exemplo.

## Reproduza

Esta parte não tem bloco próprio: ela lê o repositório na versão 2.11.4 e a mesma execução da Aula 0.2. As regras dos gates estão em docs/guide/07-interaction-modes.md e as paradas que sempre acontecem em docs/guide/04-phases-and-stages.md, na tag v2.11.4 do repositório awslabs/aidlc-workflows. Numa execução sua, todo gate espera uma mensagem sua. A instalação e a configuração do AI-DLC 2.11.4 estão testadas na descrição da Aula 0.1. Rodar o agente consome o seu plano ou a sua API.

## Exercício

Dois momentos. A verificação falhou, e corrigir mudava o desenho aprovado. E o agente quis rodar um comando antes do plano aprovado. Parou ou seguiu?

<details><summary>Uma boa resposta</summary>

Na falha, parou. O agente mostrou o que passou, o que falhou e duas opções, e não rodou de novo antes da escolha. No comando, a guarda do plano recusou e disse o próximo passo: escrever o plano. O agente escreveu e parou na pergunta, menos de dois minutos depois. Quando a correção cabia no plano aprovado, o agente corrigiu sozinho e contou. Na primeira Unit, no relatório da falha; na terceira, na pergunta de aprovação.

</details>

## Fontes

- awslabs/aidlc-workflows v2.11.4 (commit 61fdb12, 13/11/2026): docs/guide/07-interaction-modes.md, docs/guide/04-phases-and-stages.md, docs/guide/05-scopes-and-depth.md, docs/guide/13-customization.md, docs/guide/glossary.md e AGENTS.md
- laboratório: Claude Code 2.1.327 a 2.1.330 com o Sonnet 5.5, sete sessões de 18 a 20/11/2026 (consultados em 21/11/2026)
