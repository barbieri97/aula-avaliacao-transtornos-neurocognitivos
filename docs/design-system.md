# O design system das aulas

O que este repositório traz: um design system **local**, escrito em `aulas/`, sem tema npm
(`theme: none` no headmatter). Trocar por um tema pronto, ou gerar outro DS do zero, é assunto
de [`temas.md`](temas.md).

Este arquivo é o contrato: o que existe, quando usar cada coisa e as armadilhas do Slidev que
já custaram um slide.

---

## A ideia visual

Um impresso acadêmico, não uma apresentação corporativa: **papel** claro em vez de branco,
**tinta azul-marinho**, e **ouro** só onde a aula quer que o olho pare. O que separa dois
blocos aqui é um fio de cabelo ou uma lavagem pastel — nunca uma sombra.

Três decisões sustentam o resto:

- **Serifa nos títulos, sans no corpo.** O título é a fala do professor; o corpo é o que fica
  no caderno. O contraste entre as duas famílias é o que dá voz ao deck.
- **Capa, seção e fecho rodam sobre o marinho; o miolo, sobre o papel.** Fundo escuro
  significa que a aula mudou de estado. É o ritmo do deck, e é de graça: os três layouts
  compartilham a classe `.ds-inverso`.
- **A lombada.** Todo slide de miolo tem, na margem esquerda, um fio vertical com um tique de
  ouro no alto e o número da página no pé. Quem desenha isso é `aulas/lib/Moldura.vue`, que os
  layouts chamam sozinhos — não é coisa de se escrever no markdown.

E uma regra de cor, que é regra didática antes de ser estética: **pastel agrupa, cor forte
significa.** Verde, âmbar e vermelho só entram quando querem dizer *preservado*, *atenção* e
*prejuízo* — num `<Perfil>`, numa `<Nota tipo="erro">`, numa coluna de comparação. Um cartão
bonito não é motivo para gastar vermelho.

---

## Onde mora cada coisa

O Slidev define a raiz do projeto como **a pasta do arquivo `.md`**. As aulas estão em
`aulas/`, então é lá dentro que ele procura tudo:

```
aulas/
├── styles/index.css     ← o único CSS que o Slidev importa (os outros entram por @import)
│   ├── fontes.css       ← @font-face das duas famílias
│   ├── fontes/          ← os .woff2, servidos pelo próprio site
│   ├── tokens.css       ← cor, tipo, espaço, forma — a identidade visual inteira
│   ├── base.css         ← como o markdown puro se parece
│   └── utilities.css    ← as classes `ds-*` que um slide pode usar
├── layouts/*.vue        ← a forma do slide (campo `layout:` do frontmatter)
├── components/*.vue     ← peças usadas dentro do slide (auto-importadas, sem `import`)
├── lib/asset.ts         ← resolve caminho de imagem contra a base do site
├── lib/Moldura.vue      ← a lombada; usada pelos layouts, não pelo markdown
└── public/              ← imagens; `/foto.png` no markdown = `aulas/public/foto.png`
```

Uma `public/` ou uma `components/` na **raiz do repositório** não seria vista por ninguém.

---

## Tokens

Toda decisão visual está em `aulas/styles/tokens.css`. Layouts e componentes só consomem
`var(--ds-*)`; nenhum escreve um hex na mão. **Mudar a identidade visual das aulas é editar
esse arquivo, e só ele** — inclusive a página inicial do site, que lê os mesmos tokens.

| grupo | tokens |
|---|---|
| identidade | `--ds-marinho` `--ds-marinho-fundo` `--ds-marinho-claro` `--ds-ouro` `--ds-ouro-forte` `--ds-ouro-luz` `--ds-papel` |
| papéis | `--ds-bg` `--ds-surface` `--ds-ink` `--ds-muted` `--ds-rule` `--ds-rule-forte` `--ds-accent` `--ds-accent-forte` `--ds-accent-2` |
| pastéis | `--ds-pastel-azul` `--ds-pastel-ouro` `--ds-pastel-verde` `--ds-pastel-terra` `--ds-pastel-cinza` |
| sinais | `--ds-ok` `--ds-warn` `--ds-danger` (+ os `-wash` de cada um) |
| translúcidos | `--ds-accent-wash` `--ds-accent-2-wash` `--ds-ink-wash` |
| tipo | `--ds-font-sans` `--ds-font-serif` `--ds-font-mono`, escala `--ds-text-xs` … `--ds-text-3xl`, `--ds-leading-*`, `--ds-tracking-kicker` |
| espaço | `--ds-space-1` … `--ds-space-8`, `--ds-pad-slide` |
| forma | `--ds-radius-sm` `--ds-radius` `--ds-radius-lg` `--ds-border` `--ds-border-thick` `--ds-shadow` |

Dois cuidados com a cor:

- **`--ds-accent` (`#947b2f`) é o ouro de preencher**: fio, régua, marcador de lista, fundo de
  chip. Para **texto pequeno sobre papel** use `--ds-accent-forte`, que é o mesmo ouro
  escurecido até passar no contraste. Os kickers e os rótulos daqui usam o forte.
- **Sobre o marinho tudo inverte.** Em vez de repintar cada peça, os layouts escuros ganham a
  classe `.ds-inverso` (definida no fim de `base.css`), que redefine `--ds-bg`, `--ds-ink`,
  `--ds-muted`, `--ds-rule` e o ouro. Componente que só usa token funciona nos dois fundos sem
  saber onde está.

O deck é **claro só**: não existe bloco `.dark`, e as aulas trazem `colorSchema: light` no
headmatter. É uma escolha de projeção em sala com luz acesa.

### A escala de tipo

Sete tamanhos, começando em **14 px**. Nada abaixo disso entra num slide — o texto é lido do
fundo do auditório, não da mesa. Quando um slide parece precisar de um corpo menor, o problema
é conteúdo demais, e a solução é outro slide.

### Fontes

**Newsreader** (serifa, títulos) e **Source Sans 3** (sans, corpo), as duas sob SIL Open Font
License, servidas pelo próprio site a partir de `aulas/styles/fontes/`.

Não se usa o campo `fonts:` do headmatter (que puxa do Google Fonts em tempo de exibição) de
propósito: o deck é exibido em sala, às vezes sem rede, e é impresso em PDF por um navegador
headless no CI. Fonte que depende de rede vira fallback do sistema na hora errada — e aí todo
o espaçamento do slide muda. Para trocar de família, veja
[`aulas/styles/fontes/LICENCA.md`](../aulas/styles/fontes/LICENCA.md).

---

## Layouts

Vão no campo `layout:` do frontmatter do slide. Os campos de cada um viram props.

| layout | quando usar | campos |
|---|---|---|
| `default` | o slide comum (é o que vale sem `layout:`) | — |
| `capa` | o primeiro slide da aula · **fundo marinho** | `kicker` `title` `subtitle` `imagem` `meta` |
| `secao` | a virada de assunto · **fundo marinho** | `numero` `kicker` `title` `note` |
| `roteiro` | o índice da aula; repita com `atual:` diferente | `kicker` `title` `itens[]` `atual` |
| `destaque` | uma frase sozinha na tela: a tese, o número | `kicker` `title` `fonte` |
| `pergunta` | a pergunta antes da resposta · **fundo azul pastel** | `kicker` `title` `pistas[]` |
| `caso` | a ficha do caso à esquerda, a discussão à direita | `rotulo` `title` `dados[]` |
| `comparacao` | a tabela de diferencial: 2 ou 3 colunas, linha a linha | `title` `colunas[]` `linhas[]` |
| `esquema` | o slide cujo conteúdo é um desenho | `kicker` `title` `legenda` |
| `figura` | quando a imagem **é** o argumento e o texto comenta | `imagem` `legenda` `lado` `ajuste` |
| `fecho` | o último slide · **fundo marinho** | `kicker` `title` `pontos[]` `proximo` |

Os layouts do próprio Slidev continuam valendo (`center`, `two-cols`, `image-right`, `full`,
`none`…), mas eles não desenham a lombada — quem quiser a moldura usa os daqui.

Campos marcados como "aceita HTML" nos comentários de cada `.vue` são renderizados com
`v-html`: dá para escrever `<span class="ds-em">assim</span>` dentro de um título.

## Componentes

Ficam em `aulas/components/` e são **auto-importados**: basta escrever a tag no markdown.

| componente | quando usar |
|---|---|
| `<Nota>` | o aparte: `tipo` = `info` (padrão), `ok`, `alerta`, `erro` |
| `<Termo>` | a definição formal — o verbete que a turma copia |
| `<Citacao>` | a palavra de outra pessoa, dentro de um slide com mais coisas |
| `<Grade>` + `<Cartao>` | comparar coisas do mesmo tipo, 2 ou 3 colunas |
| `<Dado>` | o número que a turma tem de levar embora |
| `<Criterios>` | critérios A, B, C… — a lista que se lê inteira |
| `<LinhaDoTempo>` | sequência com marcos: história ou processo |
| `<Fluxo>` | etapas encadeadas, com a seta em SVG |
| `<Continuum>` | a faixa que mostra que duas categorias são pontos de uma linha |
| `<Perfil>` | o gráfico de perfil: um domínio por linha, escore padronizado em barra |
| `<Legenda>` | a chave de cores de um esquema |
| `<Fonte>` | o crédito no pé do slide |

Os três de esquema (`<Fluxo>`, `<Continuum>`, `<Perfil>`) desenham em **SVG inline**, com
classe no lugar de cor literal — por isso eles seguem os tokens e funcionam no PDF. Vão bem
dentro do layout `esquema`, que dá a eles o slide inteiro.

## Utilitários

`ds-kicker` `ds-lead` `ds-muted` `ds-em` `ds-em-2` `ds-grifo` `ds-small` `ds-num` `ds-grid`
`ds-stack` `ds-rule`. O UnoCSS do Slidev também está ligado (`text-sm`, `mt-4`, `grid`…) —
use-o para ajuste pontual, e as classes `ds-*` para o que tem significado editorial.

### Marcar uma palavra-chave

No corpo do slide, com o `v-mark` do Slidev (rough-notation). A cor vem de uma classe, não de
um hex — a marca é um `<svg>` anexado ao `<body>`, fora do alcance de `<style scoped>`:

```md
<span v-mark="{ at: 2, type: 'underline', class: 'ds-marca-ouro' }">só depois do clique</span>
<span v-mark="{ at: true, type: 'circle', class: 'ds-marca-marinho' }">de saída</span>
```

Classes disponíveis: `ds-marca-ouro`, `ds-marca-marinho`, `ds-marca-ok`, `ds-marca-erro`.
Tipos úteis: `underline`, `circle`, `box`, `strike-through`, `highlight`.

Duas regras práticas:

- **Marque palavra, não oração.** O rough-notation desenha em volta da caixa do elemento; num
  trecho que quebra em duas linhas, o círculo vira uma elipse por cima do parágrafo inteiro.
- **Em frontmatter não cabe diretiva do Vue.** Ali o grifo é a classe `ds-grifo`, que pinta
  uma faixa de ouro atrás da palavra: `title: Rastreio <span class="ds-grifo">não é</span> diagnóstico`.

Para ver tudo renderizado em vez de lido: **`npm run ref`** abre `aulas/_design-system.md`,
que tem um slide por layout e por componente, com a situação de uso nas notas. O nome começa
com `_`, então o site não o publica.

---

## As armadilhas do Slidev

As quatro coisas abaixo não são opinião de estilo. São comportamentos do Slidev que fazem um
slide sumir ou uma imagem quebrar **só depois de publicado**. `npm run lint` pega as três
primeiras.

### 1. `src:` no frontmatter apaga o slide

`src` é o campo com que o Slidev importa **outro arquivo `.md`** no lugar do slide. Um
`src: /foto.png` faz o Slidev tentar importar `/foto.png` como markdown: o slide desaparece do
deck, sem mensagem de erro nenhuma. Por isso o layout `figura` chama o campo de `imagem`.

### 2. Os campos que o Slidev não entrega ao layout

Estes nomes são consumidos pelo Slidev e **nunca chegam como prop**:

```
clicks · clicksStart · disabled · hide · hideInToc · layout · level · preload
routeAlias · src · title · transition · zoom · dragPos · lang · clickAnimation
```

`title` é o caso que mais aparece, porque é natural querer escrever o título do slide no
frontmatter. Ele chega pelo objeto `frontmatter`, que todo layout recebe inteiro:

```vue
const props = defineProps<{ frontmatter?: Record<string, any> }>()
const title = props.frontmatter?.title
```

Todos os layouts daqui fazem assim. O lint reclama de qualquer layout que declare uma prop com
nome reservado.

### 3. Caminho de imagem que chega por prop precisa de `asset()`

O Vite reescreve caminhos que consegue ver no build — `![](/foto.png)` no markdown, ou
`<img src="/foto.png">` escrito literalmente no template. Um caminho que chega por prop é só
uma string em tempo de execução: o Vite não a enxerga, e no GitHub Pages (onde o site vive em
`/<repo>/<slug>/`) o navegador pede a imagem na raiz do domínio e leva 404.

Localmente a base é `/` e tudo funciona — **o erro só aparece depois do deploy.** Por isso
`aulas/lib/asset.ts`, e por isso `figura.vue` e `capa.vue` passam o caminho por ele.

### 4. Markdown dentro de componente precisa de linha em branco

Sem linha em branco, o conteúdo entre as tags é tratado como HTML puro e o `**negrito**`
aparece literal na tela:

```md
<Nota titulo="Assim não">
Isto sai com os **asteriscos** à mostra.
</Nota>

<Nota titulo="Assim sim">

Isto sai com o **negrito** certo.

</Nota>
```

Vale em qualquer nível de aninhamento — `<Cartao>` dentro de `<Grade>` também precisa.

### E uma do YAML, que quebra o build e não o slide

Valor de frontmatter com **`: ` no meio** (`meta: 2 horas · leitura: DSM-5-TR`) ou com
**vírgula dentro de um mapa em chave** (`{ campo: Evolução, valor: 2 anos, lenta }`) não é o
que você acha que é: no primeiro caso o YAML vê um mapa aninhado e falha; no segundo, a
vírgula abre um novo campo. Nos dois, a solução é aspa:

```yaml
meta: "2 horas · leitura: DSM-5-TR"
- { campo: Evolução, valor: "2 anos, lenta" }
```

O lint lê o headmatter do mesmo jeito que o build lê e aponta o erro antes.

---

## As regras de sempre

- **Todo frontmatter é cercado por `---` em cima e embaixo.** Entre dois slides sem corpo
  aparecem duas linhas `---` seguidas — está certo. Compartilhar um `---` entre dois blocos
  quebra o parse do arquivo inteiro.
- **O bloco de abertura é headmatter e frontmatter do primeiro slide ao mesmo tempo.** O
  `title:` dele é o título do deck **e** o título que a `capa` mostra: não repita o campo.
- **CSS solto num slide é sinal de que falta um layout ou um componente.** A exceção honesta
  é o desenho que só existe naquele slide (o catálogo de cores em `_design-system.md` é um
  exemplo). Se você escreveria o mesmo `<style>` duas vezes, vire componente.
- **Medida em `ch` mora no elemento que tem o corpo grande.** `max-width: 24ch` num contêiner
  de corpo base não limita um `<h1>` de 54 px — limita a caixa a 24 caracteres *do corpo
  base*, e o título quebra a cada palavra.
- Um layout ou componente novo **ganha um slide em `aulas/_design-system.md`**. É o que
  mantém o catálogo confiável.
