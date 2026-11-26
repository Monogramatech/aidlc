# Aula 1.3, Parte 1: Catorze agentes, um maestro e um motor

**No vídeo:** Quem trabalha no AI-DLC: 14 agentes, um maestro e um motor

Vídeo da playlist "Curso de AI-DLC: desenvolvimento com agentes de IA, da ideia ao deploy", no canal MonogramaTech no YouTube.

## O que esta parte mostra

Quem trabalha dentro do AI-DLC: catorze agentes, um maestro que conduz a conversa e um motor que guarda a rota. Antes da primeira etapa, a primeira resposta do motor ao agente foi uma ordem: leia o pedido, proponha um plano e não crie nada.

Nesta parte você vê:
- os catorze agentes: onze especialistas amplos, dois revisores que só revisam e o compositor;
- por que tão poucos: dezenas de especialistas estreitos recriariam as passagens de bastão da cascata;
- os revisores: em que etapas entram, o que leem e o veredito pronto ou não pronto;
- o maestro e o motor: o maestro executa o passo e conversa com você, e o motor, determinístico, guarda a rota entre as etapas;
- o motor na captura: as primeiras respostas dele, e as 85 vezes que o maestro perguntou o próximo passo;
- como cada etapa roda: na conversa, num subagente, numa corrente ou em grupo.

Laboratório: aidlc-workflows v2.11.4 (commit 61fdb12) no Claude Code, com o Sonnet 5.5, na execução da Aula 0.2 (sete sessões de 18 a 20/11/2026); o repositório suporta outros harnesses, e o curso usa um, sem ranking. O app de chamados é um exemplo.

## Reproduza

Esta parte não tem bloco próprio: ela lê o repositório na versão 2.11.4 e a mesma execução da Aula 0.2. Os 14 agentes ficam em core/agents/ e o modo de cada etapa no campo mode do arquivo dela, em core/aidlc-common/stages/, na tag v2.11.4 do repositório awslabs/aidlc-workflows. Numa execução sua, você vê o maestro chamar o motor com aidlc engine orchestrate next a cada passo. A instalação e a configuração do AI-DLC 2.11.4 estão testadas na descrição da Aula 0.1. Rodar o agente consome o seu plano ou a sua API.

## Exercício

No feature, numa etapa de desenho da Construction, o revisor de arquitetura diz que o trabalho não está pronto. O que acontece, e quem põe limite?

<details><summary>Uma boa resposta</summary>

O agente líder refaz o trabalho para tratar os achados, e o revisor confere de novo. O cartão da etapa marca no máximo duas rodadas, e quem faz cumprir o limite é o motor. Se sobrar achado, o trabalho segue com os achados anotados. Nesta execução, o revisor de arquitetura disse não pronto sete vezes. Em seis delas, o trabalho virou pronto na segunda rodada. Na Unit da infraestrutura, a segunda rodada não terminou: o revisor não gravou a revisão, duas vezes. Pela regra do motor, contou como não pronto, e a Unit seguiu.

</details>

## Fontes

- awslabs/aidlc-workflows v2.11.4 (commit 61fdb12, 13/11/2026): docs/guide/06-agents.md, docs/guide/glossary.md, docs/reference/17-skill-system.md, core/agents/ e o cabeçalho de core/aidlc-common/stages/
- laboratório: Claude Code 2.1.327 a 2.1.330 com o Sonnet 5.5, sete sessões de 18 a 20/11/2026 (consultados em 21/11/2026)
