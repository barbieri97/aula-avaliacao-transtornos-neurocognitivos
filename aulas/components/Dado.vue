<!--
  <Dado> — o número que a turma tem de levar embora. Um por slide; dois ou
  três dentro de uma <Grade>, quando eles se comparam.

  <Dado numero="8,5%" rotulo="prevalência de demência acima de 60 anos, no Brasil" />

  `numero` é curto por definição: se não cabe em quatro ou cinco caracteres,
  provavelmente é uma frase, e frase é conteúdo de slide, não <Dado>.
  `rotulo` e `nota` aceitam HTML.
-->
<script setup lang="ts">
defineProps<{
  numero?: string
  rotulo?: string
  nota?: string
}>()
</script>

<template>
  <div class="ds-dado">
    <p class="numero ds-num">{{ numero }}</p>
    <p v-if="rotulo" class="rotulo" v-html="rotulo" />
    <p v-if="nota" class="nota" v-html="nota" />
  </div>
</template>

<style scoped>
.ds-dado {
  padding-top: var(--ds-space-3);
  border-top: var(--ds-border-thick) solid var(--ds-ouro);
}

.numero {
  margin: 0;
  max-width: none;
  color: var(--ds-ink);
  font-family: var(--ds-font-serif);
  font-size: var(--ds-text-3xl);
  font-weight: 600;
  line-height: 1;
  letter-spacing: -0.02em;
}

.rotulo {
  margin: var(--ds-space-2) 0 0;
  max-width: 26ch;
  font-size: var(--ds-text-sm);
  line-height: var(--ds-leading-normal);
}

.nota {
  margin: var(--ds-space-1) 0 0;
  max-width: 26ch;
  color: var(--ds-muted);
  font-size: var(--ds-text-xs);
  line-height: var(--ds-leading-normal);
}
</style>
