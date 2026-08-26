<!--
  secao — a virada de assunto. Papel, como todo o resto do deck, com o número
  da parte desenhado em contorno grande na faixa direita: é o respiro entre
  dois blocos da aula.

  Sem o fundo escuro (o template do evento pede papel em todo slide), quem
  marca a virada é o numeral e a régua de ouro sob o kicker.

  ---
  layout: secao
  numero: "02"
  kicker: Parte 2
  title: O que o rastreio não responde
  note: Uma frase dizendo por que este bloco existe.
  ---

  `kicker`, `title` e `note` aceitam HTML.
-->
<script setup lang="ts">
// `title` chega pelo objeto `frontmatter`, não como prop — ver o comentário em capa.vue.
const props = defineProps<{
  numero?: string
  kicker?: string
  note?: string
  frontmatter?: Record<string, any>
}>()

const title = props.frontmatter?.title
</script>

<template>
  <div class="slidev-layout ds-secao">
    <span v-if="numero" class="numeral" aria-hidden="true">{{ numero }}</span>

    <div class="texto">
      <p v-if="kicker" class="ds-kicker" v-html="kicker" />
      <div class="ds-rule" />
      <h1 v-if="title" v-html="title" />
      <p v-if="note" class="note" v-html="note" />
    </div>
  </div>
</template>

<style scoped>
.ds-secao {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
}

.texto {
  position: relative;
  z-index: 1;
  max-width: 58%;
}

/* A régua entre o kicker e o título: é ela, e não mais o fundo escuro, que
   anuncia que a aula mudou de bloco. */
.texto .ds-rule {
  margin-top: 0;
}

.ds-secao :deep(h1) {
  margin: 0;
  padding-bottom: var(--ds-space-4);
  font-size: 3rem;
  line-height: 1.08;
}

.note {
  max-width: 40ch;
  margin: var(--ds-space-4) 0 0;
  color: var(--ds-muted);
  font-size: var(--ds-text-lg);
  line-height: var(--ds-leading-normal);
}

/* O numeral é só contorno: presença sem peso, e não disputa leitura com o
   título. `-webkit-text-stroke` é suportado pelo Chromium, que é quem exibe e
   quem exporta o PDF.

   Sobre papel o contorno é o ouro de preencher, e não o ouro claro: ele passa
   por cima da marca-d'água sem sumir nela nem virar uma segunda mancha. */
.numeral {
  position: absolute;
  top: 50%;
  right: 3.2rem;
  transform: translateY(-50%);
  color: transparent;
  font-family: var(--ds-font-serif);
  font-size: 15rem;
  font-weight: 600;
  line-height: 1;
  letter-spacing: -0.04em;
  -webkit-text-stroke: 2px rgba(148, 123, 47, 0.55);
}
</style>
