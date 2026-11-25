# Aula 1.2, Parte 1: Onze escopos, da correção de bug ao trabalho regulado

**No vídeo:** Os 11 escopos do AI-DLC: quem escolhe e quanto cada um roda

Vídeo da playlist "Curso de AI-DLC: desenvolvimento com agentes de IA, da ideia ao deploy", no canal MonogramaTech no YouTube.

## O que esta parte mostra

Os 11 escopos do AI-DLC, a linha de produção de cada trabalho. Quatro pedidos de uma linha, em quatro conversas novas, receberam quatro planos diferentes: bugfix, refactor, infra e workshop, de 5 a 22 etapas.

Nesta parte você vê:
- o que o escopo decide: quais etapas rodam, a profundidade dos documentos (mínimo, padrão, abrangente), a estratégia de teste e as paradas;
- quem escolhe: o agente propõe um plano a partir do seu pedido, lendo as palavras-dica de cada escopo, e você decide numa pergunta antes de o trabalho começar;
- as três saídas da pergunta: seguir, usar outro plano ou montar um sob medida;
- o classic, o padrão quando ninguém propõe nem escolhe;
- os onze lado a lado, de 5 a 30 etapas, e a recomendação do guia: na dúvida, comece pelo menor que serve.

Laboratório: aidlc-workflows v2.11.4 (commit 61fdb12) no Claude Code, com o Sonnet 5.5, numa sessão curta de 21/11/2026 (quatro pedidos, parando na pergunta do plano) e na sessão 1 do fio condutor; o repositório suporta outros harnesses, e o curso usa um, sem ranking. Os pedidos da sessão são exemplos de trabalho.

## Reproduza

Esta parte não tem bloco próprio. Para ver a pergunta do plano, instale e configure o AI-DLC 2.11.4 como na descrição da Aula 0.1, abra o Claude Code numa pasta nova e digite um pedido de uma linha começando por /aidlc. Pare na primeira pergunta: ela traz o plano proposto, as etapas e os pontos de aprovação. Você chega à mesma pergunta, mas não necessariamente ao mesmo plano nem ao mesmo texto: quem lê o pedido é o agente. Os 11 escopos e as palavras-dica ficam em core/scopes/, na tag v2.11.4 do repositório awslabs/aidlc-workflows. Rodar o agente consome o seu plano ou a sua API.

## Exercício

Que escopo você escolheria para três trabalhos? Corrigir uma vulnerabilidade de segurança já publicada, testar uma ideia num protótipo e construir um serviço regulado.

<details><summary>Uma boa resposta</summary>

Para a vulnerabilidade, o security-patch. Ele roda as etapas do bugfix e mais uma, que registra a exigência de segurança: sete ao todo, em profundidade mínima. Para o protótipo, o poc: cinco etapas, para provar a ideia rápido e chegar logo ao código. E para o serviço regulado, o enterprise: as 30 etapas, com documentos e testes no nível abrangente. Repare nas dicas, na tela: as do poc e as do security-patch descrevem esses trabalhos. O enterprise não tem nenhuma: o agente usa a descrição, ou você pede pelo nome.

</details>

## Fontes

- awslabs/aidlc-workflows v2.11.4 (commit 61fdb12, 13/11/2026): docs/guide/05-scopes-and-depth.md e core/scopes/aidlc-*.md
- laboratório: Claude Code 2.1.330 com o Sonnet 5.5, sessão curta de 21/11/2026 e sessão 1 do fio condutor (18/11/2026) (consultados em 21/11/2026)
