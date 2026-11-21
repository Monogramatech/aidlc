# Aula 0.1, Parte 1: Do assistente de código ao ciclo auditável

**No vídeo:** O que é AI-DLC: o agente pergunta antes de programar

Vídeo da playlist "Curso de AI-DLC: desenvolvimento com agentes de IA, da ideia ao deploy", no canal MonogramaTech no YouTube.

## O que esta parte mostra

O que é o AI-DLC, o ciclo de desenvolvimento guiado por IA da AWS: um pedido de uma linha ao agente, e em 11,5 segundos voltou uma pergunta, com um plano de 19 etapas e 19 pontos de aprovação, e nenhuma linha de código.

Nesta parte você vê:
- o ciclo de sempre e os dois jeitos comuns de a IA entrar nele, segundo a AWS: como assistente e como autônoma;
- o assistente que esquece, e a memória de contexto: o que fica gravado no projeto, e não só na conversa;
- a conversa invertida do método de 2025: a IA planeja e pergunta, e as pessoas decidem (supervisão humana);
- as três fases do método, a Mob Elaboration e o PRFAQ;
- o repositório awslabs/aidlc-workflows v2.11.4: um núcleo, sete harnesses, cinco fases, 33 etapas e quatro princípios;
- a execução real: o agente chama o motor do AI-DLC, propõe o escopo mvp e devolve a pergunta do plano;
- a pasta do intent, que guarda o que você decidiu de uma sessão para outra.

Laboratório: aidlc-workflows v2.11.4 (commit 61fdb12) no Claude Code 2.1.327, com o Sonnet 5.5, execução de 18/11/2026; o repositório suporta outros harnesses, e o curso usa um, sem ranking. O app de chamados é um exemplo. Primeira parte do curso de AI-DLC em português.

## Reproduza

Os passos do laboratório no Windows, num PowerShell sem administrador, com o Claude Code já instalado: o aidlc-workflows na versão 2.11.4 (nunca o latest), a configuração de uma pasta nova e o pedido, que se digita dentro do Claude Code. Rodar o agente consome o seu plano ou a sua API. Você vai ver os mesmos passos e a mesma parada para a sua decisão, mas não o mesmo texto: o agente responde diferente a cada execução, e pode propor outro escopo.

```powershell
# 1. Instalação (PowerShell sem administrador, numa pasta de rascunho curta e fora do OneDrive)
irm https://github.com/awslabs/aidlc-workflows/releases/download/v2.11.4/install.ps1 -OutFile install.ps1
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass -Force
./install.ps1 -Version 2.11.4

# 2. Abra um PowerShell novo, volte à pasta de rascunho e configure o projeto
aidlc version
mkdir aula-0-1
cd aula-0-1
git init -q
git config user.name "Aluno do curso"
git config user.email "aluno@example.com"
aidlc config --harness claude --mcp none --yes
aidlc config models --preset balanced --project --yes
aidlc doctor

# 3. Abra o Claude Code nesta pasta e, dentro dele, digite o pedido da linha seguinte
claude --model sonnet --permission-mode manual --strict-mcp-config
# /aidlc Quero um app de chamados de suporte priorizados por urgência
```

O bloco é o mesmo da descrição do vídeo. Ele foi testado por script em 18/11/2026, numa pasta limpa: a instalação, a configuração e o `aidlc doctor`. O pedido ao agente não entra no teste.

## Exercício

Na Inception, o agente pergunta se o app precisa de login. Quem decide, quem escreve o arquivo de requisitos, e quem diz se ficou certo?

<details><summary>Uma boa resposta</summary>

O login é decisão sua, porque é o que construir. O agente escreve o arquivo de requisitos, com as suas respostas e o conhecimento dele. Quem diz se ficou certo é você, num gate de aprovação: a parada no fim da etapa, que espera a sua decisão. O plano do mvp tinha 19 deles.

</details>

## Fontes

- awslabs/aidlc-workflows v2.11.4 (commit 61fdb12, 13/11/2026): README.md, AGENTS.md (The four tenets), CHANGELOG.md, docs/guide/03-spaces-and-intents.md, docs/guide/04-phases-and-stages.md, docs/guide/05-scopes-and-depth.md e docs/guide/glossary.md
- AWS DevOps Blog, AI-Driven Development Life Cycle (Raja SP, 31/07/2025)
- AI-DLC Method Definition (Raja SP, AWS), seções II.2, III.2, III.3 e IV.1
- laboratório: Claude Code 2.1.327 com o Sonnet 5.5, execução de 18/11/2026 (consultados em 17 e 18/11/2026)
