<!--
  <Legenda> — a chave de cores de um esquema. Vai logo abaixo de um <Perfil>,
  de um <Continuum> ou de uma figura com áreas coloridas.

  <Legenda :itens="[
    { cor: 'ok', texto: 'dentro do esperado' },
    { cor: 'warn', texto: 'limítrofe' },
    { cor: 'danger', texto: 'abaixo do esperado' },
  ]" />

  `cor` usa o mesmo vocabulário do resto do design system:
  `azul` · `ouro` · `verde` · `terra` · `cinza` são os pastéis (os mesmos de
  <Cartao>, <Fluxo> e <Continuum>); `marinho`, `ok`, `warn` e `danger` são as
  cores fortes (as mesmas de <Perfil> e <Nota>). `texto` aceita HTML.
-->
<script setup lang="ts">
defineProps<{
  itens?: { cor?: string, texto?: string }[]
}>()
</script>

<template>
  <ul class="ds-legenda">
    <li v-for="(item, i) in itens" :key="i">
      <span class="chip" :class="`cor-${item.cor ?? 'marinho'}`" />
      <span v-html="item.texto" />
    </li>
  </ul>
</template>

<style scoped>
.ds-legenda {
  display: flex;
  flex-wrap: wrap;
  gap: var(--ds-space-2) var(--ds-space-5);
  margin: var(--ds-space-3) 0;
  padding: 0;
  max-width: none;
  list-style: none;
}

.ds-legenda li {
  display: flex;
  align-items: center;
  gap: var(--ds-space-2);
  margin: 0;
  padding: 0;
  color: var(--ds-muted);
  font-size: var(--ds-text-xs);
}

/* O `content: none` desarma o quadradinho que base.css põe em todo <li>: aqui
   o marcador é o próprio chip de cor. */
.ds-legenda li::before {
  content: none;
}

.chip {
  width: 0.85rem;
  height: 0.85rem;
  flex: none;
  border: 1px solid var(--ds-rule-forte);
}

/* fortes */
.cor-marinho { background: var(--ds-marinho); }
.cor-ok { background: var(--ds-ok); }
.cor-warn { background: var(--ds-warn); }
.cor-danger { background: var(--ds-danger); }

/* pastéis */
.cor-azul { background: var(--ds-pastel-azul); }
.cor-ouro { background: var(--ds-pastel-ouro); }
.cor-verde { background: var(--ds-pastel-verde); }
.cor-terra { background: var(--ds-pastel-terra); }
.cor-cinza { background: var(--ds-pastel-cinza); }
</style>
