<!--
  slide-bottom — a marca-d'água da Giunti, atrás do conteúdo de TODO slide.

  Não é um componente de markdown nem um layout: `slide-bottom.vue` é um nome
  que o Slidev procura na raiz do projeto (aqui, `aulas/`) e renderiza dentro
  de cada slide, ANTES do layout. Por isso o desenho fica atrás do texto sem
  que nenhum layout precise saber que ele existe — e vale igual na
  apresentação e na exportação em PDF.

  A geometria vem do template da Giunti, onde a mesma arte entra como
  `mask.png` ocupando a faixa `x=43% … 100%` do slide, de topo a pé. O .pptx
  fica em `referencias/`, fora do repositório: ele é material interno da
  Giunti e o site é público. A imagem já é translúcida (azul #006EB7 a 20%), então
  ela não precisa de opacidade nem de blend: basta ser desenhada por baixo.

  O par disto é `slide-top.vue`, que põe o logotipo por cima.
-->
<script setup lang="ts">
// `asset()` porque o caminho chega como string em tempo de execução — o Vite
// não o reescreve, e sem a base do site a imagem some depois do deploy.
// Ver docs/design-system.md → "Caminho de imagem que chega por prop".
import { asset } from './lib/asset'

const marca = asset('/image1.png')
</script>

<template>
  <div class="ds-marca-dagua" aria-hidden="true">
    <img :src="marca" alt="">
  </div>
</template>

<style scoped>
/* 57% é a largura da faixa no template. A arte é quase quadrada (1705×1683) e
   preenche essa faixa exatamente num slide 16:9 — `contain` é só a garantia de
   que ela não distorce se a proporção do deck mudar. */
.ds-marca-dagua {
  position: absolute;
  top: 0;
  right: 0;
  width: 57%;
  height: 100%;
  pointer-events: none;
}

.ds-marca-dagua img {
  width: 100%;
  height: 100%;
  border-radius: 0;
  object-fit: contain;
  object-position: right center;
}
</style>
