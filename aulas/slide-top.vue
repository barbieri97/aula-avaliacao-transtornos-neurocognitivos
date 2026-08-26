<!--
  slide-top — o logotipo Giunti Psychometrics · Vetor Editora, por cima de todo
  slide.

  Como `slide-bottom.vue`, é um nome que o Slidev procura na raiz do projeto e
  renderiza em cada slide — este DEPOIS do layout, para que nenhum fundo de
  cartão ou de tabela o cubra.

  Duas posições, as duas tiradas do template da Giunti:

    miolo   canto inferior direito (x=70,6% · y=91% · w=24,7% no template).
            Aqui o logo é alinhado pela margem do slide, e não pela medida do
            template, para bater com o rodapé de <Fonte> e com a lombada.
    capa    canto superior esquerdo, logo acima do título (x=4,9% · y=10,1% ·
            w=38,9%). No template ele alinha com o título — por isso aqui ele
            alinha com a margem esquerda do texto, que é onde o título começa.

  O layout do slide vem de `$frontmatter`, que o Slidev injeta por slide. É a
  única coisa que este arquivo precisa saber sobre o deck.
-->
<script setup lang="ts">
import { useSlideContext } from '@slidev/client'
import { asset } from './lib/asset'

const { $frontmatter } = useSlideContext()

const logo = asset('/image2.png')
const naCapa = $frontmatter?.layout === 'capa'
</script>

<template>
  <img
    class="ds-logo"
    :class="{ capa: naCapa }"
    :src="logo"
    alt="Giunti Psychometrics · Vetor Editora"
  >
</template>

<style scoped>
/* `right`/`bottom` batem com a margem direita do slide e com a linha de base
   do <Fonte> — por isso o rodapé de crédito para em 33% de largura: é o que
   sobra à esquerda do logo. */
.ds-logo {
  position: absolute;
  right: 3.2rem;
  bottom: 1.1rem;
  width: 24.7%;
  height: auto;
  border-radius: 0;
  pointer-events: none;
}

/* Na capa o logo troca de canto e cresce: ele é a primeira coisa do slide, e
   o título vem logo abaixo (a `capa` reserva o espaço com `padding-top`). */
.ds-logo.capa {
  top: 10.1%;
  left: 4.4rem;
  right: auto;
  bottom: auto;
  width: 34%;
}
</style>
