<!--
  esquema — o slide cujo conteúdo é um desenho. Título em cima, o desenho
  ocupando tudo o que sobra, legenda embaixo. Use com os componentes de
  esquema (<Fluxo>, <Continuum>, <Perfil>) ou com um SVG escrito à mão.

  ---
  layout: esquema
  title: Do rastreio ao diagnóstico
  legenda: Cada seta é uma decisão, não uma etapa obrigatória.
  ---

  <Fluxo :etapas="[…]" />

  `title` e `legenda` aceitam HTML. O corpo é centralizado nos dois eixos e
  nunca ultrapassa a área do slide.
-->
<script setup lang="ts">
// `title` chega pelo objeto `frontmatter`, não como prop — ver o comentário em capa.vue.
import Moldura from '../lib/Moldura.vue'

const props = defineProps<{
  kicker?: string
  legenda?: string
  frontmatter?: Record<string, any>
}>()

const title = props.frontmatter?.title
</script>

<template>
  <div class="slidev-layout ds-esquema">
    <Moldura />
    <div class="topo">
      <p v-if="kicker" class="ds-kicker" v-html="kicker" />
      <h1 v-if="title" v-html="title" />
    </div>

    <div class="palco"><slot /></div>

    <p v-if="legenda" class="legenda ds-small" v-html="legenda" />
  </div>
</template>

<style scoped>
.ds-esquema {
  position: relative;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.topo {
  flex: none;
}

.ds-esquema :deep(h1) {
  margin-bottom: var(--ds-space-4);
}

/* `min-height: 0` é o que impede o desenho de empurrar a legenda para fora do
   slide: sem ele, um item de flex nunca encolhe abaixo do conteúdo. */
.palco {
  display: flex;
  flex-direction: column;
  justify-content: center;
  flex: 1;
  min-height: 0;
}

.palco :deep(> :first-child) {
  margin-top: 0;
}

.palco :deep(> :last-child) {
  margin-bottom: 0;
}

.legenda {
  flex: none;
  margin: var(--ds-space-4) 0 0;
  padding-top: var(--ds-space-3);
  max-width: none;
  border-top: var(--ds-border) solid var(--ds-rule);
}
</style>
