<!--
  Moldura — a lombada do slide: o fio vertical na margem esquerda e o fólio.

  NÃO é um componente de uso no markdown (por isso mora em `lib/` e não em
  `components/`): quem a coloca é o layout, uma vez, e todo slide de miolo sai
  com a mesma marca. Os layouts invertidos (capa, secao, fecho) não a usam —
  ali a página é a marca.

  O número vem de `$page`, que o Slidev injeta por slide; funciona igual no
  modo de apresentação e na exportação em PDF, onde todos os slides são
  montados de uma vez.
-->
<script setup lang="ts">
import { useSlideContext } from '@slidev/client'

withDefaults(defineProps<{ folio?: boolean }>(), { folio: true })

const { $page } = useSlideContext()
</script>

<template>
  <div class="ds-moldura" aria-hidden="true">
    <span class="fio" />
    <span v-if="folio" class="folio ds-num">{{ String($page).padStart(2, '0') }}</span>
  </div>
</template>

<style scoped>
.ds-moldura {
  position: absolute;
  top: 2.4rem;
  bottom: 1.5rem;
  left: 2.1rem;
  width: 1.4rem;
  pointer-events: none;
}

/* O fio para antes do fólio para não encostar no número. */
.fio {
  position: absolute;
  top: 0;
  bottom: 2rem;
  left: 0;
  width: 1px;
  background: var(--ds-rule);
}

/* O primeiro pedaço do fio é dourado: é o que marca o alto da página. */
.fio::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 3px;
  height: 1.8rem;
  background: var(--ds-ouro);
}

.folio {
  position: absolute;
  bottom: 0;
  left: -0.1rem;
  color: var(--ds-muted);
  font-family: var(--ds-font-sans);
  font-size: var(--ds-text-xs);
  font-weight: 600;
  letter-spacing: 0.06em;
}
</style>
