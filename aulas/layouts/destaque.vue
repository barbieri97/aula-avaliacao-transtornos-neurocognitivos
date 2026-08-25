<!--
  destaque — uma frase sozinha na tela. A tese, o número que assusta, a
  definição que a aula inteira desdobra. Papel, tipo grande em serifa, nada
  mais.

  ---
  layout: destaque
  kicker: O ponto
  title: Rastreio <span class="ds-grifo">não é</span> diagnóstico.
  fonte: DSM-5-TR, 2022
  ---

  `kicker`, `title` e `fonte` aceitam HTML. Para grifar uma palavra no título
  use `class="ds-grifo"` — dentro de frontmatter não cabe diretiva do Vue, e
  portanto não cabe `v-mark`.
-->
<script setup lang="ts">
// `title` chega pelo objeto `frontmatter`, não como prop — ver o comentário em capa.vue.
import Moldura from '../lib/Moldura.vue'

const props = defineProps<{
  kicker?: string
  fonte?: string
  frontmatter?: Record<string, any>
}>()

const title = props.frontmatter?.title
</script>

<template>
  <div class="slidev-layout ds-destaque">
    <Moldura />
    <div class="bloco">
      <p v-if="kicker" class="ds-kicker" v-html="kicker" />
      <div class="ds-rule" />
      <h1 v-if="title" v-html="title" />
      <div class="corpo"><slot /></div>
      <p v-if="fonte" class="fonte ds-small" v-html="fonte" />
    </div>
  </div>
</template>

<style scoped>
.ds-destaque {
  position: relative;
  display: flex;
  align-items: center;
  height: 100%;
}

/* O `ch` mede o corpo do ELEMENTO em que está escrito. Posto no bloco (que
   herda o corpo base), 24ch dariam uma coluna de 230px e o título de 54px
   quebraria a cada palavra — por isso a medida vive no h1. */
.ds-destaque :deep(h1) {
  max-width: 24ch;
  margin: 0;
  padding: 0;
  font-size: var(--ds-text-3xl);
  line-height: 1.1;
}

/* Aqui a régua vem ANTES do título, então o fio automático embaixo do h1 sobra. */
.ds-destaque :deep(h1::after) {
  display: none;
}

.corpo:not(:empty) {
  max-width: 44ch;
  margin-top: var(--ds-space-5);
  color: var(--ds-muted);
  font-size: var(--ds-text-lg);
}

.fonte {
  margin: var(--ds-space-5) 0 0;
}
</style>
