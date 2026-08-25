<!--
  <LinhaDoTempo> — sequência com marcos. Serve para história do conceito e
  também para processo ("o que acontece em cada etapa").

  <LinhaDoTempo :itens="[
    { quando: '1907', o_que: 'Alzheimer', desc: 'o caso de Auguste D.' },
    { quando: '2013', o_que: 'DSM-5', desc: 'demência vira transtorno neurocognitivo' },
  ]" />

  `desc` é opcional. `o_que` e `desc` aceitam HTML.
-->
<script setup lang="ts">
defineProps<{
  itens?: { quando?: string, o_que?: string, desc?: string }[]
}>()
</script>

<template>
  <ol class="ds-linha">
    <li v-for="(item, i) in itens" :key="i">
      <span class="quando ds-num">{{ item.quando }}</span>
      <span class="texto">
        <span class="o-que" v-html="item.o_que" />
        <span v-if="item.desc" class="desc" v-html="item.desc" />
      </span>
    </li>
  </ol>
</template>

<style scoped>
/* O fio vertical é a borda esquerda da lista; cada marca é um ::before
   posicionado em cima dele. Sem pseudo-elemento no <li> não há como manter o
   alinhamento quando um item tem duas linhas de texto. */
.ds-linha {
  display: grid;
  gap: var(--ds-space-5);
  margin: var(--ds-space-5) 0;
  padding: 0 0 0 var(--ds-space-5);
  max-width: none;
  border-left: 1px solid var(--ds-rule-forte);
  list-style: none;
}

.ds-linha li {
  position: relative;
  display: flex;
  align-items: baseline;
  gap: var(--ds-space-4);
  margin: 0;
  padding: 0;
}

/* Um quadrado, e não um círculo: é o mesmo marcador das listas do deck. */
.ds-linha li::before {
  content: "";
  position: absolute;
  top: 0.5em;
  left: calc(-1 * var(--ds-space-5) - 5px);
  width: 9px;
  height: 9px;
  border: 2px solid var(--ds-bg);
  background: var(--ds-ouro);
}

/* Largura fixa, não `min-width`: com min-width um rótulo comprido empurra só a
   sua linha para a direita e a coluna dos títulos sai torta. */
.quando {
  flex: 0 0 5rem;
  color: var(--ds-accent-forte);
  font-size: var(--ds-text-sm);
  font-weight: 700;
}

.texto {
  display: flex;
  flex-direction: column;
  gap: 0.1rem;
}

.o-que {
  font-size: var(--ds-text-lg);
  font-weight: 600;
  line-height: var(--ds-leading-tight);
}

.desc {
  color: var(--ds-muted);
  font-size: var(--ds-text-sm);
}
</style>
