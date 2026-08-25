<!--
  <Cartao> — um bloco de conteúdo com título. Um conceito por cartão.

  <Cartao rotulo="domínio 3" titulo="Aprendizagem e memória" cor="ouro">

  Evocação livre, evocação com pista, reconhecimento.

  </Cartao>

  `cor`: nenhuma (padrão) · azul · ouro · verde · terra · cinza — a lavagem
  pastel serve para agrupar cartões que são do mesmo tipo, não para enfeitar.
  `destaque` põe o cartão em ouro; use em no máximo um por grade, senão nenhum
  se destaca.
-->
<script setup lang="ts">
withDefaults(defineProps<{
  rotulo?: string
  titulo?: string
  cor?: 'nenhuma' | 'azul' | 'ouro' | 'verde' | 'terra' | 'cinza'
  destaque?: boolean
}>(), { cor: 'nenhuma' })
</script>

<template>
  <div class="ds-cartao" :class="[`cor-${cor}`, { destaque }]">
    <p v-if="rotulo" class="rotulo">{{ rotulo }}</p>
    <p v-if="titulo" class="titulo">{{ titulo }}</p>
    <div class="corpo"><slot /></div>
  </div>
</template>

<style scoped>
/* Sem sombra: o que separa o cartão do papel é o fio de cabelo e, quando há,
   a lavagem. Sombra em slide projetado vira borrão. */
.ds-cartao {
  display: flex;
  flex-direction: column;
  gap: var(--ds-space-1);
  padding: var(--ds-space-3) var(--ds-space-4);
  border: var(--ds-border) solid var(--ds-rule-forte);
  background: var(--ds-surface);
}

.ds-cartao.cor-azul {
  border-color: transparent;
  background: var(--ds-pastel-azul);
}

.ds-cartao.cor-ouro {
  border-color: transparent;
  background: var(--ds-pastel-ouro);
}

.ds-cartao.cor-verde {
  border-color: transparent;
  background: var(--ds-pastel-verde);
}

.ds-cartao.cor-terra {
  border-color: transparent;
  background: var(--ds-pastel-terra);
}

.ds-cartao.cor-cinza {
  border-color: transparent;
  background: var(--ds-pastel-cinza);
}

.ds-cartao.destaque {
  border-color: var(--ds-ouro);
  border-top-width: var(--ds-border-thick);
  background: var(--ds-accent-wash);
}

.rotulo {
  margin: 0;
  max-width: none;
  color: var(--ds-accent-forte);
  font-size: var(--ds-text-xs);
  font-weight: 700;
  letter-spacing: var(--ds-tracking-kicker);
  text-transform: uppercase;
}

.titulo {
  margin: 0;
  max-width: none;
  font-family: var(--ds-font-serif);
  font-size: var(--ds-text-lg);
  font-weight: 600;
  line-height: var(--ds-leading-tight);
}

.corpo {
  font-size: var(--ds-text-sm);
  line-height: var(--ds-leading-normal);
}

.corpo :deep(p) {
  margin: var(--ds-space-2) 0 0;
  max-width: none;
  line-height: var(--ds-leading-normal);
}

.corpo :deep(> :first-child) {
  margin-top: 0;
}

.corpo :deep(> :last-child) {
  margin-bottom: 0;
}
</style>
