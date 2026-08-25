---
theme: none
title: Design system — catálogo
info: Um slide por layout e por componente, com a situação de uso nas notas
date: "2026-09-01"
colorSchema: light
layout: capa
kicker: Deck de bancada
subtitle: Um slide para cada <span class="ds-em">layout</span> e cada <span class="ds-em">componente</span>. Abra com <code>npm run ref</code>.
imagem: /capa-perfil.svg
meta: O nome começa com <code>_</code>, então o site não publica este deck. Ele existe para você ver antes de escrever.
---

<!--
Este é o catálogo do design system: a versão renderizada do que docs/design-system.md
descreve por escrito. Toda vez que você criar um layout ou componente novo em aulas/,
acrescente um slide aqui — é o que mantém o catálogo confiável.

O slide que você está vendo é o layout `capa`, com o campo `imagem`.
-->

---
layout: roteiro
kicker: O que tem aqui
title: O catálogo
itens:
  - { tema: Tokens, desc: cor, tipo e espaço — o vocabulário }
  - { tema: Layouts, desc: "11 locais, incluindo o `default`" }
  - { tema: Componentes, desc: "13 peças para usar dentro do slide" }
  - { tema: Markdown puro, desc: como texto sem enfeite se parece }
atual: 1
---

---
layout: secao
numero: "01"
kicker: Parte 1
title: Tokens
note: Nenhum layout e nenhum componente escreve uma cor na mão. Todos leem daqui.
---

---
layout: default
---

# As cores

<div class="amostras">
  <div><span class="chip" style="background: var(--ds-marinho)"></span><code>--ds-marinho</code><em>a tinta</em></div>
  <div><span class="chip" style="background: var(--ds-ouro)"></span><code>--ds-ouro</code><em>a ênfase</em></div>
  <div><span class="chip" style="background: var(--ds-papel); border-color: var(--ds-rule-forte)"></span><code>--ds-papel</code><em>o fundo</em></div>
  <div><span class="chip" style="background: var(--ds-muted)"></span><code>--ds-muted</code><em>texto secundário</em></div>
  <div><span class="chip" style="background: var(--ds-pastel-azul)"></span><code>--ds-pastel-azul</code><em>agrupa</em></div>
  <div><span class="chip" style="background: var(--ds-pastel-ouro)"></span><code>--ds-pastel-ouro</code><em>agrupa</em></div>
  <div><span class="chip" style="background: var(--ds-pastel-verde)"></span><code>--ds-pastel-verde</code><em>agrupa</em></div>
  <div><span class="chip" style="background: var(--ds-pastel-terra)"></span><code>--ds-pastel-terra</code><em>agrupa</em></div>
  <div><span class="chip" style="background: var(--ds-ok)"></span><code>--ds-ok</code><em>preservado</em></div>
  <div><span class="chip" style="background: var(--ds-warn)"></span><code>--ds-warn</code><em>atenção</em></div>
  <div><span class="chip" style="background: var(--ds-danger)"></span><code>--ds-danger</code><em>prejuízo</em></div>
  <div><span class="chip" style="background: var(--ds-surface); border-color: var(--ds-rule-forte)"></span><code>--ds-surface</code><em>cartões</em></div>
</div>

<Fonte>Trocar a identidade visual das aulas = editar <code>aulas/styles/tokens.css</code>, e só ele.</Fonte>

<style>
.amostras {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--ds-space-2) var(--ds-space-5);
  margin-top: var(--ds-space-4);
}
.amostras > div { display: flex; align-items: center; gap: var(--ds-space-2); font-size: var(--ds-text-xs); }
.amostras .chip {
  width: 1.6rem; height: 1.6rem; flex: none;
  border: 1px solid transparent;
}
.amostras em { color: var(--ds-muted); font-style: normal; }
</style>

<!--
Este slide usa um <style> local — a exceção que confirma a regra. Ele desenha uma amostra de
cor, que só existe neste catálogo. Numa aula, CSS solto é sinal de que falta um layout ou um
componente.
-->

---
layout: default
---

# A escala de tipo

<div class="escala">
  <p style="font-size: var(--ds-text-3xl); font-family: var(--ds-font-serif)">3xl — capa e destaque</p>
  <p style="font-size: var(--ds-text-2xl); font-family: var(--ds-font-serif)">2xl — título de slide</p>
  <p style="font-size: var(--ds-text-xl); font-family: var(--ds-font-serif)">xl — título de bloco</p>
  <p style="font-size: var(--ds-text-lg)">lg — abertura e item de lista</p>
  <p style="font-size: var(--ds-text-base)">base — o corpo do slide</p>
  <p style="font-size: var(--ds-text-sm)">sm — legenda e corpo de cartão</p>
  <p style="font-size: var(--ds-text-xs)">xs — rótulo e crédito</p>
</div>

<Fonte>Serifa (Newsreader) nos títulos, sans (Source Sans 3) no corpo. A escala começa em 14&nbsp;px: slide é para ser lido do fundo da sala.</Fonte>

<style>
.escala p { margin: 0.15rem 0; max-width: none; line-height: 1.25; }
</style>

---
layout: secao
numero: "02"
kicker: Parte 2
title: Layouts
note: A forma do slide. Vai no campo `layout:` do frontmatter — e escolher o certo é o que dispensa CSS solto.
---

---
layout: destaque
kicker: layout destaque
title: Uma frase <span class="ds-grifo">sozinha</span> na tela.
fonte: Campos — kicker · title · fonte. O corpo do slide, se houver, entra abaixo em cinza.
---

<!--
Use para a tese, a pergunta que abre a discussão ou o número que assusta. Uma frase por
slide: se são duas, são dois slides.
-->

---
layout: pergunta
kicker: layout pergunta
title: A pergunta vai antes da resposta?
pistas:
  - As pistas ficam nesta faixa, no pé.
  - No máximo três — elas são pistas, não a resposta.
---

<v-click>

O corpo do slide é a resposta. Envolvê-lo em `<v-click>` faz a turma tentar antes de ler.

</v-click>

<!--
O fundo azul pastel é a marca deste layout: a turma reconhece de longe que ali é a vez dela.
-->

---
layout: caso
rotulo: Caso clínico
title: Sra. M., 68 anos
dados:
  - { campo: Escolaridade, valor: 11 anos }
  - { campo: Queixa, valor: "troca nomes de objetos", destaque: true }
  - { campo: Evolução, valor: 8 meses }
---

## layout caso

A ficha da esquerda fica igual em todos os slides do mesmo caso; muda só a discussão.

- `dados` aceita quantos campos couberem — cinco ou seis é o confortável
- `destaque: true` marca em ouro o dado que a discussão vai puxar

<Nota titulo="Por que a ficha não rola">

Se a ficha não cabe, o caso está com dado demais para um slide. Divida em dois.

</Nota>

---
layout: comparacao
title: layout comparacao
colunas:
  - { titulo: Coluna A, sub: pastel ouro, cor: ouro }
  - { titulo: Coluna B, sub: pastel azul, cor: azul }
  - { titulo: Coluna C, sub: pastel verde, cor: verde }
linhas:
  - { criterio: Critério, valores: [valor, valor, valor] }
  - { criterio: Outro, valores: [a lavagem corre pela coluna inteira, "e é ela que amarra o cabeçalho aos valores", sem borda vertical nenhuma] }
  - { criterio: Teto, valores: [duas colunas leem melhor, três ainda funcionam, na quarta ninguém lê a linha] }
---

---
layout: esquema
title: layout esquema
legenda: Título em cima, o desenho ocupando tudo o que sobra, legenda embaixo. É o layout dos componentes de esquema.
---

<Fluxo :etapas="[
  { titulo: 'Uma etapa', desc: 'com descrição curta' },
  { titulo: 'Outra', desc: 'a seta é SVG, não caractere' },
  { titulo: 'A última', desc: 'destacada em ouro', cor: 'ouro' },
]" />

---
layout: figura
imagem: /curva-normal.svg
legenda: A legenda pendura num fio de ouro — o mesmo gesto do fio embaixo do título.
lado: direita
---

# layout figura

Campos: `imagem` · `legenda` · `lado` (direita ou esquerda) · `ajuste` (contain ou cover).

O campo é `imagem`, **nunca** `src`: `src` é reservado pelo Slidev e faz o slide sumir sem
erro nenhum.

---
layout: secao
numero: "03"
kicker: Parte 3
title: Componentes
note: As peças que vão dentro do slide. São auto-importadas — basta escrever a tag no markdown.
---

---
layout: default
---

# Nota, nos quatro tipos

<Nota titulo="info — o padrão">

O aparte que comenta. Marinho, sem urgência nenhuma.

</Nota>

<Nota tipo="ok" titulo="ok">

O que está preservado, o caminho certo, a boa prática.

</Nota>

<Nota tipo="alerta" titulo="alerta">

O que exige cautela: a norma errada, o corte que não se aplica.

</Nota>

<Nota tipo="erro" titulo="erro">

O atalho que invalida a conclusão. Cor forte porque o conteúdo é forte.

</Nota>

---
layout: default
---

# Termo, Citacao e Fonte

<Termo palavra="Verbete" origem="a definição que a turma copia">

Fio grosso de ouro em cima, palavra em serifa. `origem` é a procedência: o manual, o autor,
a etimologia.

</Termo>

<Citacao autor="Autora citada" fonte="Revista, ano">

A palavra de outra pessoa, dentro de um slide com outras coisas.

</Citacao>

<Fonte>&lt;Fonte&gt; fica ancorada no pé do slide, alinhada com a lombada — e não empurra o conteúdo.</Fonte>

---
layout: default
---

# Grade, Cartao e Dado

<Grade :cols="3">

<Cartao rotulo="rotulo" titulo="Cartão simples">

Fio de cabelo, sem sombra.

</Cartao>

<Cartao titulo="Com lavagem" cor="ouro">

`cor` agrupa cartões do mesmo tipo.

</Cartao>

<Cartao titulo="Em destaque" destaque>

No máximo um por grade.

</Cartao>

</Grade>

<Grade :cols="3">

<Dado numero="2%" rotulo="da população fica abaixo de −2 DP" nota="por definição da curva" />

<Dado numero="6" rotulo="domínios cognitivos no DSM-5-TR" />

<Dado numero="14%" rotulo="fica entre −1 e −2 DP" nota="a faixa limítrofe" />

</Grade>

---
layout: default
---

# Criterios e LinhaDoTempo

<Criterios :itens="[
  { titulo: 'A letra entra sozinha', texto: 'A, B, C… a menos que você escreva a sua em <code>letra</code>.' },
  { titulo: 'Cinco itens é o teto', texto: 'Acima disso o slide vira página de manual — e ninguém lê manual projetado.' },
]" />

<LinhaDoTempo :itens="[
  { quando: '1907', o_que: 'Um marco', desc: 'a data fica numa coluna fixa, à esquerda' },
  { quando: '2013', o_que: 'Outro', desc: 'serve para história e também para processo' },
]" />

---
layout: esquema
title: Perfil, Continuum e Legenda
legenda: Os três esquemas em SVG. As cores saem dos tokens — nenhum hex é escrito dentro do componente.
---

<Perfil :dominios="[
  { nome: 'Um domínio', z: -0.4 },
  { nome: 'Outro domínio', z: -1.6 },
  { nome: 'Um terceiro', z: -2.4 },
]" />

<Continuum :marcos="[
  { rotulo: 'Primeiro trecho', nota: 'com uma nota' },
  { rotulo: 'Segundo', nota: 'em destaque', destaque: true },
  { rotulo: 'Terceiro', nota: 'a ponta diz que a linha continua' },
]" />

<Legenda :itens="[
  { cor: 'ok', texto: 'dentro do esperado' },
  { cor: 'warn', texto: 'limítrofe' },
  { cor: 'danger', texto: 'rebaixado' },
]" />

---
layout: default
---

# Markdown puro

Texto corrido, com **negrito em ouro**, *itálico* e [link](https://sli.dev).

- Item de lista, com o marcador quadrado em ouro
- Outro item
  - Sublinha, menor e em cinza

> Uma citação em bloco, em serifa, com o fio de ouro à esquerda.

| Coluna | Outra |
|---|---|
| Linha sem grade | só o filete |
| Cabeçalho em caixa alta | e fio marinho |

---
layout: default
---

# As marcas de palavra-chave

Uma palavra recebe a marca do rough-notation ao clique —
<span v-mark="{ at: 1, type: 'underline', class: 'ds-marca-ouro' }">assim</span> — ou já de
saída, com <code>at: true</code>:
<span v-mark="{ at: true, type: 'circle', class: 'ds-marca-marinho' }">assim</span>.

Dentro de frontmatter não cabe diretiva do Vue: lá o grifo é a classe
<span class="ds-grifo">ds-grifo</span>, que pinta a faixa por baixo da palavra.

<Nota tipo="alerta" titulo="Marque palavra, não frase">

O rough-notation desenha em volta da caixa do elemento. Num trecho que quebra em duas linhas,
o círculo vira uma elipse gigante por cima do parágrafo inteiro — marque uma ou duas palavras,
nunca uma oração.

</Nota>

---
layout: fecho
kicker: Antes de escrever
title: As regras que sobrevivem a tudo
pontos:
  - "<code>src:</code> no frontmatter apaga o slide. Use outro nome de campo."
  - Caminho de imagem que chega por prop passa por <code>asset()</code>.
  - Todo frontmatter é cercado por <code>---</code> em cima e embaixo.
  - Markdown dentro de componente precisa de linha em branco.
proximo: <code>npm run lint</code> pega as três primeiras. Rode antes de commitar.
---
