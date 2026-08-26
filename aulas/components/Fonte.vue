<!--
  <Fonte> — o crédito no pé do slide, ancorado embaixo à esquerda, alinhado
  com a lombada.

  <Fonte>APA, <em>DSM-5-TR</em>, 2022 · tradução da autora</Fonte>

  Fica em `position: absolute`, então não empurra o conteúdo: pode aparecer em
  qualquer posição do markdown do slide. Para em 33% da largura porque o canto
  inferior direito é do logotipo da Giunti (ver `slide-top.vue`).
-->
<template>
  <p class="ds-fonte">
    <slot />
  </p>
</template>

<style scoped>
.ds-fonte {
  position: absolute;
  left: 4.4rem;
  right: 33%;
  bottom: 1.1rem;
  margin: 0;
  max-width: none;
  color: var(--ds-muted);
  font-size: var(--ds-text-xs);
  line-height: var(--ds-leading-normal);
}
</style>
