# AI-DLC: o agente faz, você decide

Os comandos e as respostas dos exercícios do curso **"AI-DLC: o agente faz, você decide"**, do canal MonogramaTech no YouTube
(playlist "Curso de AI-DLC: desenvolvimento com agentes de IA, da ideia ao deploy").
O curso ensina o AI-DLC (AI-Driven Development Life Cycle) da AWS para programadores de qualquer stack, a partir do repositório
[awslabs/aidlc-workflows](https://github.com/awslabs/aidlc-workflows) na versão 2.11.4. Toda tela do agente nos vídeos saiu de uma
execução real.

Curso independente, sem vínculo com a AWS. AWS e os nomes de ferramentas citados são marcas dos seus donos.

## O que você precisa

- Windows com PowerShell: os comandos de instalação usam o instalador oficial do `aidlc-workflows`, que é um script PowerShell;
- Git;
- um harness de agente. O curso usa o Claude Code, já instalado e autenticado. O `aidlc-workflows` também suporta Kiro CLI, Kiro IDE,
  Codex CLI, Cursor, opencode e GitHub Copilot; a ordem não é ranking.

Rodar o agente consome o seu plano ou a sua API.

## Comece aqui

```powershell
git clone https://github.com/Monogramatech/aidlc.git
```

Depois abra o README da parte (`aulas/<parte>/README.md`) e siga o bloco "Reproduza", num PowerShell sem administrador.
Ele promete os mesmos passos, a mesma estrutura de arquivos e as mesmas paradas para a sua aprovação. O texto do agente muda a cada
execução.

## As partes

| Parte | Tema | Reproduza | Exercícios |
| --- | --- | --- | --- |
| [0.1 · Parte 1](aulas/0.1-parte-1/) | Do assistente de código ao ciclo auditável | sim | 1 |
| [0.2 · Parte 1](aulas/0.2-parte-1/) | Um pedido, cinco fases | — | 1 |

Cada pasta tem um README com o que a parte mostra, o bloco "Reproduza", os exercícios com uma boa resposta e as fontes.

## Licenças

- O código está sob a licença MIT: veja [LICENSE](LICENSE).
- Os textos (os README, os comandos comentados e as respostas dos exercícios) estão sob a CC BY 4.0: veja
  [LICENSE-CC-BY-4.0](LICENSE-CC-BY-4.0). Pode reutilizar e adaptar, citando a fonte: "AI-DLC: o agente faz, você decide", canal MonogramaTech.
