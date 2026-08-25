<!--
  <Nota> — o aparte. O que não é o fio da aula, mas não pode passar batido.

  <Nota tipo="alerta" titulo="Cuidado">

  Escolaridade baixa derruba o escore do MEEM sem que haja declínio.

  </Nota>

  tipo: info (padrão) · ok · alerta · erro

  A regra de cor do design system vale aqui: `ok`, `alerta` e `erro` são cores
  fortes e têm significado. Uma nota que só comenta é `info`.
-->
<script setup lang="ts">
withDefaults(defineProps<{
  tipo?: 'info' | 'ok' | 'alerta' | 'erro'
  titulo?: string
}>(), { tipo: 'info' })
</script>

<template>
  <aside class="ds-nota" :class="tipo">
    <p v-if="titulo" class="titulo">{{ titulo }}</p>
    <div class="corpo"><slot /></div>
  </aside>
</template>

<style scoped>
/* `--cor` e `--fundo` são os dois pontos de variação entre os quatro tipos:
   o fio da esquerda, o rótulo e a lavagem saem deles. */
.ds-nota {
  --cor: var(--ds-marinho);
  --fundo: var(--ds-pastel-azul);
  max-width: 46rem;
  margin: var(--ds-space-5) 0;
  padding: var(--ds-space-3) var(--ds-space-5);
  border-left: var(--ds-border-thick) solid var(--cor);
  background: var(--fundo);
}

.ds-nota.ok {
  --cor: var(--ds-ok);
  --fundo: var(--ds-ok-wash);
}

.ds-nota.alerta {
  --cor: var(--ds-warn);
  --fundo: var(--ds-warn-wash);
}

.ds-nota.erro {
  --cor: var(--ds-danger);
  --fundo: var(--ds-danger-wash);
}

.titulo {
  margin: 0 0 var(--ds-space-1);
  max-width: none;
  color: var(--cor);
  font-size: var(--ds-text-xs);
  font-weight: 700;
  letter-spacing: var(--ds-tracking-kicker);
  text-transform: uppercase;
}

.corpo {
  font-size: var(--ds-text-sm);
  line-height: var(--ds-leading-normal);
}

.corpo :deep(> :first-child) {
  margin-top: 0;
}

.corpo :deep(> :last-child) {
  margin-bottom: 0;
}

/* A caixa já limita a medida de leitura; sem soltar o `max-width` do
   parágrafo, o texto pararia bem antes da borda e o bloco ficaria oco. */
.corpo :deep(p) {
  margin: var(--ds-space-2) 0;
  max-width: none;
  line-height: var(--ds-leading-normal);
}
</style>
