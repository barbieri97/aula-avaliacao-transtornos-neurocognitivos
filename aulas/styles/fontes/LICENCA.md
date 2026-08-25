# Fontes

Os quatro `.woff2` desta pasta são os subsets `latin` de duas famílias do Google Fonts,
baixados uma vez e versionados aqui para que o deck não dependa de rede — nem em sala, nem
no navegador headless que exporta o PDF no CI.

| arquivo | família | licença |
|---|---|---|
| `newsreader-latin.woff2`, `newsreader-latin-italic.woff2` | [Newsreader](https://fonts.google.com/specimen/Newsreader) | SIL Open Font License 1.1 |
| `source-sans-3-latin.woff2`, `source-sans-3-latin-italic.woff2` | [Source Sans 3](https://fonts.google.com/specimen/Source+Sans+3) | SIL Open Font License 1.1 |

As duas são fontes variáveis: um arquivo por estilo (romano e itálico) cobre toda a faixa de
peso. As declarações `@font-face` estão em `aulas/styles/fontes.css`.

Para trocar de fonte: baixe o `.woff2` do subset `latin`, ponha aqui, ajuste o `@font-face` e
o token `--ds-font-sans` / `--ds-font-serif` em `tokens.css`.
