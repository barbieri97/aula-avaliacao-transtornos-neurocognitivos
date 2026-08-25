<!--
  default — o slide comum, sobrescrevendo o `default` do Slidev.

  Existe por um motivo só: dar ao slide sem `layout:` a mesma lombada (o fio na
  margem esquerda com o número da página) que os outros layouts daqui têm. O
  conteúdo é o markdown puro, formatado por styles/base.css.

  ---
  layout: default    # ou simplesmente omitir o campo
  ---

  # Título do slide

  Texto, listas, componentes.
-->
<script setup lang="ts">
import Moldura from '../lib/Moldura.vue'
</script>

<template>
  <div class="slidev-layout default ds-slide">
    <Moldura />
    <slot />
  </div>
</template>

<style scoped>
.ds-slide {
  position: relative;
  height: 100%;
}
</style>
