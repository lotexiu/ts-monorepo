# aleph-typescript

Monorepo (pnpm workspaces + Turborepo) que reúne minhas bibliotecas TypeScript e os apps que as consomem. Cada pacote vive em seu próprio repositório e entra aqui como submódulo git.

## Pacotes (`packages/`)

| Pacote | Descrição |
|---|---|
| [`typescript`](https://github.com/lotexiu/typescript) | Núcleo sem dependência de framework: signals/computed, máscara de input, gerenciadores de teclado, mouse e tema, paleta de cores. |
| [`react`](https://github.com/lotexiu/react) | Adaptador React: hooks sobre signals (compatível com SSR e React Compiler). Veja [README-ReactWrapper.md](README-ReactWrapper.md). |
| [`br`](https://github.com/lotexiu/br) | CPF, CNPJ (alfanumérico), CEP, telefone e UF como dados validados por vetores de teste. |
| [`vite-utils`](https://github.com/lotexiu/vite-utils) | Plugins Vite para build das bibliotecas. |
| [`eslint-config`](https://github.com/lotexiu/eslint-config) | Configurações de ESLint compartilhadas. |
| [`typescript-config`](https://github.com/lotexiu/typescript-config) | `tsconfig.json` compartilhados. |

## Apps (`apps/`)

[`angular-desk`](https://github.com/lotexiu/angular-desk), [`react-desk`](https://github.com/lotexiu/react-desk) e [`svelte-desk`](https://github.com/lotexiu/svelte-desk).

## Como rodar

Requisitos: Node.js e [pnpm](https://pnpm.io).

```sh
git clone https://github.com/lotexiu/ts-monorepo.git
cd ts-monorepo
pnpm start      # sincroniza os submódulos e instala as dependências
pnpm build      # build de todos os pacotes (turbo)
pnpm dev        # modo de desenvolvimento
```

Outros scripts úteis: `pnpm format` (Prettier), `pnpm upd` (atualiza dependências), `pnpm outd` (lista desatualizadas) e `pnpm clean` (remove `node_modules` e limpa o cache).

## Estrutura

```
ts-monorepo/
├── apps/        # angular-desk, react-desk, svelte-desk (submódulos)
├── packages/    # typescript, react, br, vite-utils, eslint-config, typescript-config
├── turbo.json   # pipeline de build, lint e dev
└── pnpm-workspace.yaml
```
