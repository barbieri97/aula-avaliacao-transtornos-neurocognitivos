<!--
  capa — o primeiro slide da aula. É o único slide com imagem sangrando na
  borda, e um dos três que rodam sobre o marinho (os outros são `secao` e
  `fecho`). O contraste entre esses três e o papel do miolo é o que dá ritmo
  ao deck: fundo escuro = a aula mudou de estado.

  ---
  layout: capa
  kicker: Aula 01 · Psicologia
  subtitle: A pergunta que a aula responde.
  imagem: /capa-exemplo.svg     # opcional, ocupa a faixa direita
  meta: 4 de setembro · 2h · turma da manhã
  ---

  `title` costuma vir do headmatter (no primeiro slide o bloco é headmatter e
  frontmatter ao mesmo tempo) — não repita o campo.
  `kicker`, `subtitle` e `meta` aceitam HTML.
-->
<script setup lang="ts">
// `title` é campo reservado do Slidev: ele o usa para o índice e NÃO o repassa como prop.
// O jeito de lê-lo é pelo objeto `frontmatter`, que chega inteiro em todo layout.
// Ver docs/design-system.md → "Os campos que o Slidev não entrega".
import { asset } from '../lib/asset'

const props = defineProps<{
  kicker?: string
  subtitle?: string
  meta?: string
  imagem?: string
  frontmatter?: Record<string, any>
}>()

const title = props.frontmatter?.title
const arquivo = asset(props.imagem)
</script>

<template>
  <div class="slidev-layout ds-capa ds-inverso" :class="{ 'com-imagem': arquivo }">
    <div class="texto">
      <p v-if="kicker" class="ds-kicker" v-html="kicker" />
      <h1 v-if="title" v-html="title" />
      <div class="ds-rule" />
      <p v-if="subtitle" class="ds-lead" v-html="subtitle" />
      <div class="corpo"><slot /></div>
    </div>

    <figure v-if="arquivo" class="faixa">
      <img :src="arquivo" alt="">
    </figure>

    <p v-if="meta" class="meta ds-small" v-html="meta" />
  </div>
</template>

<style scoped>
.ds-capa {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
  padding-right: 3.2rem;
}

.ds-capa.com-imagem {
  padding-right: 38%;
}

/* O título da capa é o maior tipo do deck. Com imagem ao lado ele desce um
   degrau: a coluna de texto encolhe, e 54px em 4 linhas viraria um bloco. */
.ds-capa :deep(h1) {
  margin: 0;
  padding: 0;
  font-size: var(--ds-text-3xl);
  line-height: 1.06;
}

.ds-capa.com-imagem :deep(h1) {
  font-size: 2.9rem;
}

/* O fio de ouro embaixo do h1 é da regra geral de título de slide; na capa
   quem faz esse papel é a `.ds-rule`, que vem depois do título. */
.ds-capa :deep(h1::after) {
  display: none;
}

.ds-capa .ds-lead {
  max-width: 34ch;
  color: var(--ds-muted);
}

.corpo:not(:empty) {
  margin-top: var(--ds-space-5);
}

/* A faixa da imagem sangra até a borda: por isso `absolute`, e não uma coluna
   do grid — o padding do slide não a alcança. */
.faixa {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  width: 34%;
  margin: 0;
  border-left: 1px solid var(--ds-ouro-luz);
  overflow: hidden;
}

.faixa img {
  width: 100%;
  height: 100%;
  border-radius: 0;
  object-fit: cover;
}

.meta {
  position: absolute;
  bottom: 1.9rem;
  left: 4.4rem;
  right: 3.2rem;
  margin: 0;
  padding-top: var(--ds-space-3);
  border-top: var(--ds-border) solid var(--ds-rule);
}

.ds-capa.com-imagem .meta {
  right: 38%;
  padding-right: var(--ds-space-5);
}
</style>
