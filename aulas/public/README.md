# Imagens

**Esta pasta é a `public/` do Slidev.** O Slidev trata a pasta do arquivo `.md` como raiz do
projeto, e as aulas moram em `aulas/` — então é aqui que entram as imagens, e não numa
`public/` na raiz do repositório. O caminho dentro do markdown é absoluto e sem o nome da
pasta: `/curva-normal.svg`.

| arquivo | serve para |
|---|---|
| `capa-perfil.svg` | a faixa da direita no layout `capa` — barras de um perfil, em ouro sobre marinho |
| `curva-normal.svg` | a distribuição normal com as faixas esperada, limítrofe e rebaixada |
| `teste-do-relogio.svg` | dois protocolos do teste do desenho do relógio, lado a lado |

São SVGs escritos à mão, nas cores do design system (`--ds-marinho` `#242258`, `--ds-ouro`
`#947b2f`, os pastéis e os sinais). Pesam poucos KB, escalam sem borrar e se editam em
qualquer editor de texto.

## Imagem carregada como `<img>` não enxerga o CSS do deck

Um SVG aqui dentro é carregado como arquivo: ele não herda as fontes nem as variáveis
`--ds-*` do slide. Duas consequências práticas:

- **Cor** vai literal no arquivo (é a única exceção à regra de não escrever hex fora dos
  tokens). Se você mudar a paleta em `tokens.css`, estes arquivos precisam ser atualizados na
  mão.
- **Texto** dentro do SVG cai para a fonte do sistema; por isso os rótulos aqui são curtos e
  usam uma pilha genérica. Quando o desenho depende da tipografia do deck, ele deve ser um
  **componente** com SVG inline (como `<Perfil>` e `<Continuum>`), não um arquivo desta pasta.

## Duas maneiras de usar, e só uma funciona sempre

```md
![alguma coisa](/curva-normal.svg)     ← o Vite reescreve este caminho no build
```

```md
---
layout: figura
imagem: /curva-normal.svg              ← chega como prop, em tempo de execução
---
```

O segundo caso **só funciona porque o layout passa o caminho por `asset()`**
(`aulas/lib/asset.ts`). Sem isso a imagem some quando o site é publicado num subdiretório —
e localmente continua aparecendo, o que faz o erro só surgir depois do deploy. Qualquer
componente novo que aceite caminho de imagem por prop precisa fazer o mesmo.
