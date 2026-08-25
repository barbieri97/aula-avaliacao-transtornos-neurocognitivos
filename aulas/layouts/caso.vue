<!--
  caso — a ficha do caso clínico à esquerda, a discussão à direita. O layout
  que sustenta a aula quando ela é conduzida por um caso: repita-o ao longo do
  deck, com a mesma ficha e discussões diferentes, e a turma volta ao caso sem
  precisar rolar a memória.

  ---
  layout: caso
  rotulo: Caso clínico
  title: Sr. J., 72 anos
  dados:
    - { campo: Escolaridade, valor: 4 anos }
    - { campo: Queixa, valor: esquece recados, destaque: true }
    - { campo: Evolução, valor: 2 anos, lenta }
  ---

  O que a turma tem de fazer com o caso vai no corpo do slide.

  `destaque: true` num dado o marca em ouro — use no dado que a discussão vai
  puxar. `campo` e `valor` aceitam HTML.
-->
<script setup lang="ts">
// `title` chega pelo objeto `frontmatter`, não como prop — ver o comentário em capa.vue.
import Moldura from '../lib/Moldura.vue'

const props = withDefaults(defineProps<{
  rotulo?: string
  dados?: { campo?: string, valor?: string, destaque?: boolean }[]
  frontmatter?: Record<string, any>
}>(), { rotulo: 'Caso clínico' })

const title = props.frontmatter?.title
</script>

<template>
  <div class="slidev-layout ds-caso">
    <Moldura />

    <aside class="ficha">
      <p class="rotulo">{{ rotulo }}</p>
      <p v-if="title" class="nome" v-html="title" />
      <dl v-if="dados?.length">
        <div v-for="(dado, i) in dados" :key="i" :class="{ destaque: dado.destaque }">
          <dt v-html="dado.campo" />
          <dd v-html="dado.valor" />
        </div>
      </dl>
    </aside>

    <div class="discussao"><slot /></div>
  </div>
</template>

<style scoped>
.ds-caso {
  position: relative;
  display: grid;
  grid-template-columns: 15.5rem 1fr;
  gap: var(--ds-space-7);
  height: 100%;
}

/* A ficha é um documento dentro do slide: superfície clara, fio em volta,
   cabeçalho em caixa alta. Ela não rola nem cresce — se não couber, é a ficha
   que está com dado demais. */
.ficha {
  align-self: start;
  max-height: 100%;
  padding: var(--ds-space-4);
  border: var(--ds-border) solid var(--ds-rule-forte);
  border-top: var(--ds-border-thick) solid var(--ds-marinho);
  background: var(--ds-surface);
}

.rotulo {
  margin: 0 0 var(--ds-space-2);
  color: var(--ds-accent-forte);
  font-size: var(--ds-text-xs);
  font-weight: 700;
  letter-spacing: var(--ds-tracking-kicker);
  text-transform: uppercase;
}

.nome {
  margin: 0 0 var(--ds-space-3);
  max-width: none;
  font-family: var(--ds-font-serif);
  font-size: var(--ds-text-lg);
  font-weight: 600;
  line-height: var(--ds-leading-tight);
}

dl {
  margin: 0;
}

dl > div {
  display: grid;
  gap: 0.1rem;
  padding: var(--ds-space-2) 0;
  border-top: var(--ds-border) solid var(--ds-rule);
}

dl > div.destaque {
  margin: 0 calc(-1 * var(--ds-space-2));
  padding: var(--ds-space-2);
  border-top-color: transparent;
  background: var(--ds-accent-wash);
}

dt {
  color: var(--ds-muted);
  font-size: var(--ds-text-xs);
  letter-spacing: 0.04em;
  text-transform: uppercase;
}

dd {
  margin: 0;
  font-size: var(--ds-text-sm);
  line-height: var(--ds-leading-normal);
}

.discussao {
  min-width: 0;
  overflow: hidden;
}

.discussao :deep(> :first-child) {
  margin-top: 0;
}
</style>
