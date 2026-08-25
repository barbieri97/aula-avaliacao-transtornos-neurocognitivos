<!--
  <Criterios> — critérios diagnósticos, ou qualquer lista em que cada item
  tem uma letra e precisa ser lido inteiro. As letras entram sozinhas (A, B,
  C…), a menos que você escreva a sua em `letra`.

  <Criterios :itens="[
    { titulo: 'Declínio cognitivo', texto: 'Preocupação do próprio, de informante ou do clínico <b>e</b> prejuízo documentado.' },
    { titulo: 'Independência', texto: 'As atividades instrumentais seguem preservadas.' },
  ]" />

  `titulo` e `texto` aceitam HTML. Cinco itens é o teto de um slide.
-->
<script setup lang="ts">
const props = defineProps<{
  itens?: { letra?: string, titulo?: string, texto?: string }[]
}>()

const LETRAS = 'ABCDEFGH'
const itens = (props.itens ?? []).map((item, i) => ({
  ...item,
  letra: item.letra ?? LETRAS[i] ?? '·',
}))
</script>

<template>
  <ol class="ds-criterios">
    <li v-for="(item, i) in itens" :key="i">
      <span class="letra">{{ item.letra }}</span>
      <span class="texto">
        <span v-if="item.titulo" class="titulo" v-html="item.titulo" />
        <span v-if="item.texto" class="corpo" v-html="item.texto" />
      </span>
    </li>
  </ol>
</template>

<style scoped>
.ds-criterios {
  display: grid;
  gap: 0;
  margin: var(--ds-space-4) 0;
  padding: 0;
  max-width: none;
  list-style: none;
}

.ds-criterios li {
  display: flex;
  align-items: flex-start;
  gap: var(--ds-space-4);
  margin: 0;
  padding: var(--ds-space-3) 0;
  border-top: var(--ds-border) solid var(--ds-rule);
}

.ds-criterios li:last-child {
  border-bottom: var(--ds-border) solid var(--ds-rule);
}

/* A letra é um selo: quadrado marinho, texto papel. É o que faz a lista
   parecer um manual, que é exatamente de onde ela vem. */
.letra {
  flex: none;
  width: 1.7rem;
  height: 1.7rem;
  background: var(--ds-marinho);
  color: var(--ds-papel);
  font-family: var(--ds-font-serif);
  font-size: var(--ds-text-sm);
  font-weight: 600;
  line-height: 1.75rem;
  text-align: center;
}

.texto {
  display: flex;
  flex-direction: column;
  gap: 0.1rem;
}

.titulo {
  font-size: var(--ds-text-base);
  font-weight: 600;
}

.corpo {
  color: var(--ds-muted);
  font-size: var(--ds-text-sm);
  line-height: var(--ds-leading-normal);
}
</style>
