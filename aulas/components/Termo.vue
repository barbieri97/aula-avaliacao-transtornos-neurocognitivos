<!--
  <Termo> — a definição formal de uma palavra. O bloco que a turma copia.

  <Termo palavra="Transtorno neurocognitivo" origem="DSM-5-TR, 2022">

  Declínio **adquirido** em um ou mais domínios cognitivos, em relação a um
  nível prévio de desempenho.

  </Termo>

  `origem` é a procedência da definição: o manual, o autor, a etimologia.
-->
<script setup lang="ts">
defineProps<{
  palavra?: string
  origem?: string
}>()
</script>

<template>
  <dl class="ds-termo">
    <dt>
      <span class="palavra">{{ palavra }}</span>
      <span v-if="origem" class="origem">{{ origem }}</span>
    </dt>
    <dd><slot /></dd>
  </dl>
</template>

<style scoped>
/* Fio grosso em cima e fundo claro: o bloco tem cara de verbete, não de
   cartão. É o único componente cuja palavra-chave vem em serifa — é ela que a
   turma vai procurar depois no caderno. */
.ds-termo {
  max-width: 46rem;
  margin: var(--ds-space-5) 0;
  padding: var(--ds-space-4) var(--ds-space-5);
  border: var(--ds-border) solid var(--ds-rule-forte);
  border-top: var(--ds-border-thick) solid var(--ds-ouro);
  background: var(--ds-surface);
}

dt {
  display: flex;
  align-items: baseline;
  gap: var(--ds-space-3);
  flex-wrap: wrap;
}

.palavra {
  font-family: var(--ds-font-serif);
  font-size: var(--ds-text-xl);
  font-weight: 600;
  line-height: var(--ds-leading-tight);
}

.origem {
  color: var(--ds-muted);
  font-size: var(--ds-text-xs);
  letter-spacing: 0.04em;
  text-transform: uppercase;
}

dd {
  margin: var(--ds-space-2) 0 0;
  font-size: var(--ds-text-sm);
  line-height: var(--ds-leading-loose);
}

/* Qualificado com a classe do bloco de propósito: `dd :deep(p)` sozinho perde
   para `.slidev-layout p:not([class])` do base.css, e o texto pararia bem antes
   da borda do verbete. */
.ds-termo dd :deep(p) {
  max-width: none;
}

dd :deep(> :first-child) {
  margin-top: 0;
}

dd :deep(> :last-child) {
  margin-bottom: 0;
}
</style>
