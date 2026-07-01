# prompts

🇺🇸 [Read in English](./README.md)

Uma biblioteca pessoal e crescente de prompts que eu reutilizo com frequência em ferramentas de IA para código (GitHub Copilot, Cursor, Claude Code). Pública caso seja útil pra mais alguém — use como quiser.

## Estrutura

```
prompts/
├── coding/
│   └── general.md      # prompts reutilizáveis, agrupados por categoria
├── docs/
│   └── README.md        # filosofia, convenções, como contribuir (para humanos)
├── agents/
│   └── README.md        # a mesma informação, escrita para agentes de IA
└── CLAUDE.md             # ponto de entrada para agentes de IA
```

## Como usar

Cada prompt é uma linha: um emoji (âncora visual, não chave de busca) seguido de uma instrução pronta pra rodar. Abra [`coding/general.md`](./coding/general.md), pegue o que precisar, cole na ferramenta que estiver usando.

Pra entender a lógica por trás da estrutura e como adicionar novos prompts, veja [`/docs`](./docs/README.md) (em inglês).

## Licença

Domínio público / use como quiser — veja [LICENSE](./LICENSE).
