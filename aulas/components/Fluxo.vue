<!--
  <Fluxo> — etapas encadeadas, com a seta desenhada em SVG entre elas. É o
  esquema de processo: o que vem antes, o que vem depois, e onde a decisão
  acontece.

  <Fluxo :etapas="[
    { titulo: 'Queixa', desc: 'do paciente ou do informante' },
    { titulo: 'Rastreio', desc: 'MoCA, fluência, relógio' },
    { titulo: 'Testagem', desc: 'os seis domínios', cor: 'ouro' },
  ]" />

  `orientacao`: horizontal (padrão) · vertical — a vertical cabe mais texto por
  etapa; a horizontal mostra melhor que existe um sentido.
  `cor` de cada etapa: nenhuma (padrão) · azul · ouro · verde · terra · cinza.
-->
<script setup lang="ts">
withDefaults(defineProps<{
  etapas?: { titulo?: string, desc?: string, cor?: string }[]
  orientacao?: 'horizontal' | 'vertical'
}>(), { orientacao: 'horizontal' })
</script>

<template>
  <div class="ds-fluxo" :class="orientacao">
    <template v-for="(etapa, i) in etapas" :key="i">
      <div class="etapa" :class="`cor-${etapa.cor ?? 'nenhuma'}`">
        <span class="titulo" v-html="etapa.titulo" />
        <span v-if="etapa.desc" class="desc" v-html="etapa.desc" />
      </div>

      <svg
        v-if="i < (etapas?.length ?? 0) - 1"
        class="seta"
        viewBox="0 0 32 24"
        aria-hidden="true"
      >
        <path d="M3 12 H23" />
        <path d="M19 6.5 L26 12 L19 17.5" />
      </svg>
    </template>
  </div>
</template>

<style scoped>
.ds-fluxo {
  display: flex;
  align-items: stretch;
  gap: var(--ds-space-2);
  margin: var(--ds-space-4) 0;
}

.ds-fluxo.vertical {
  flex-direction: column;
  align-items: stretch;
}

/* Alinhado pelo topo, e não centrado: com descrições de tamanhos diferentes,
   centrar deixa os títulos das etapas em alturas diferentes — e o olho lê a
   fileira como se fossem coisas de níveis diferentes. */
.etapa {
  display: flex;
  flex-direction: column;
  gap: var(--ds-space-1);
  justify-content: flex-start;
  flex: 1;
  min-width: 0;
  padding: var(--ds-space-3) var(--ds-space-4);
  border: var(--ds-border) solid var(--ds-rule-forte);
  background: var(--ds-surface);
}

/* Cinco etapas na horizontal deixam pouco mais de 7rem por caixa: o título
   entra no corpo base, e `overflow-wrap` garante que uma palavra comprida
   quebre em vez de vazar por cima da etapa vizinha. */
.titulo {
  font-family: var(--ds-font-serif);
  font-size: var(--ds-text-base);
  font-weight: 600;
  line-height: var(--ds-leading-tight);
  overflow-wrap: anywhere;
}

.ds-fluxo.vertical .titulo {
  font-size: var(--ds-text-lg);
}

.desc {
  color: var(--ds-muted);
  font-size: var(--ds-text-xs);
  line-height: var(--ds-leading-normal);
}

/* A seta é um SVG de traço, não um caractere: assim ela tem a mesma espessura
   dos fios do deck e não depende de fonte para aparecer no PDF. */
.seta {
  flex: none;
  align-self: center;
  width: 2rem;
  height: 1.5rem;
  fill: none;
  stroke: var(--ds-ouro);
  stroke-width: 2;
  stroke-linecap: round;
  stroke-linejoin: round;
}

.ds-fluxo.vertical .seta {
  transform: rotate(90deg);
}

.cor-azul { border-color: transparent; background: var(--ds-pastel-azul); }
.cor-ouro { border-color: transparent; background: var(--ds-pastel-ouro); }
.cor-verde { border-color: transparent; background: var(--ds-pastel-verde); }
.cor-terra { border-color: transparent; background: var(--ds-pastel-terra); }
.cor-cinza { border-color: transparent; background: var(--ds-pastel-cinza); }
</style>
