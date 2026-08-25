<!--
  pergunta — o slide que abre um bloco pedindo a resposta antes de dá-la.
  Fundo em azul pastel: a turma reconhece de longe que ali é a vez dela.

  ---
  layout: pergunta
  kicker: Antes de continuar
  title: Por que <em>testar</em> se a queixa já é clara?
  pistas:
    - Quem tem queixa nem sempre tem prejuízo.
    - Quem tem prejuízo nem sempre tem queixa.
  ---

  <v-click>

  A resposta, que só aparece depois do clique.

  </v-click>

  `kicker`, `title` e cada pista aceitam HTML. O corpo do slide é a resposta —
  envolva em `<v-click>` para revelá-la na hora certa.
-->
<script setup lang="ts">
// `title` chega pelo objeto `frontmatter`, não como prop — ver o comentário em capa.vue.
import Moldura from '../lib/Moldura.vue'

const props = withDefaults(defineProps<{
  kicker?: string
  pistas?: string[]
  frontmatter?: Record<string, any>
}>(), { kicker: 'Pergunta' })

const title = props.frontmatter?.title
</script>

<template>
  <div class="slidev-layout ds-pergunta">
    <Moldura />
    <div class="topo">
      <p v-if="kicker" class="ds-kicker" v-html="kicker" />
      <h1 v-if="title" v-html="title" />
    </div>

    <div class="resposta"><slot /></div>

    <ul v-if="pistas?.length" class="pistas">
      <li v-for="(pista, i) in pistas" :key="i">
        <span class="marca ds-num">{{ i + 1 }}</span>
        <span v-html="pista" />
      </li>
    </ul>
  </div>
</template>

<style scoped>
/* O campo pastel troca o fundo do slide inteiro; os componentes que usam
   `--ds-surface` continuam se destacando porque a superfície segue quase
   branca. */
.ds-pergunta {
  --ds-bg: var(--ds-pastel-azul);
  --ds-rule: #d3d3e4;
  position: relative;
  display: flex;
  flex-direction: column;
  height: 100%;
  background: var(--ds-pastel-azul);
}

.topo {
  flex: none;
}

.ds-pergunta :deep(h1) {
  max-width: 22ch;
  margin: 0;
  padding: 0;
  font-size: 2.9rem;
  line-height: 1.12;
}

.ds-pergunta :deep(h1::after) {
  display: none;
}

/* A resposta ocupa o espaço que sobra e começa colada no topo dele: sem isto,
   um `<v-click>` curto flutua no meio do slide. */
.resposta {
  flex: 1;
  min-height: 0;
  margin-top: var(--ds-space-5);
  overflow: hidden;
}

.resposta :deep(> :first-child) {
  margin-top: 0;
}

.pistas {
  display: flex;
  gap: var(--ds-space-6);
  flex: none;
  margin: 0;
  padding: var(--ds-space-4) 0 0;
  max-width: none;
  border-top: var(--ds-border) solid var(--ds-rule-forte);
  list-style: none;
}

.pistas li {
  display: flex;
  align-items: baseline;
  gap: var(--ds-space-3);
  flex: 1;
  margin: 0;
  padding: 0;
  color: var(--ds-muted);
  font-size: var(--ds-text-sm);
  line-height: var(--ds-leading-normal);
}

.pistas li::before {
  content: none;
}

.marca {
  flex: none;
  width: 1.5rem;
  height: 1.5rem;
  border: 1px solid var(--ds-ouro);
  border-radius: 50%;
  color: var(--ds-accent-forte);
  font-size: var(--ds-text-xs);
  font-weight: 700;
  line-height: 1.45rem;
  text-align: center;
}
</style>
