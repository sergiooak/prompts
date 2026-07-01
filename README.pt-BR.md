# prompts

🇺🇸 [Read in English](./README.md)

Uma biblioteca pessoal e crescente de prompts que eu reutilizo com frequência em ferramentas de IA para código (GitHub Copilot, Cursor, Claude Code). Pública caso seja útil pra mais alguém — use como quiser.

## Estrutura

```
prompts/
├── topics/
│   └── coding/
│       ├── general.md   # prompts reutilizáveis e agnósticos de framework, agrupados por categoria
│       ├── angular.md    # prompts específicos de Angular/RxJS
│       ├── vue.md        # prompts específicos de Vue
│       └── react.md      # prompts específicos de React
└── AGENTS.md             # filosofia, convenções, como contribuir (humanos + agentes de IA)
```

## Como usar

Cada prompt é uma linha: um emoji (âncora visual, não chave de busca) seguido de uma instrução pronta pra rodar. Abra [`topics/coding/general.md`](./topics/coding/general.md) pros prompts agnósticos de framework, ou o arquivo da sua stack ([`angular.md`](./topics/coding/angular.md), [`vue.md`](./topics/coding/vue.md), [`react.md`](./topics/coding/react.md)), pegue o que precisar, cole na ferramenta que estiver usando.

Pra entender a lógica por trás da estrutura e como adicionar novos prompts, veja [`AGENTS.md`](./AGENTS.md) (em inglês).

## Licença

Domínio público / use como quiser — veja [LICENSE](./LICENSE).
