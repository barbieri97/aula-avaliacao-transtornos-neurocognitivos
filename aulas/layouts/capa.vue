<!--
  capa — o primeiro slide da aula.

  Segue o slide "Cover 1" do template da Giunti: papel claro, o logotipo no
  canto superior esquerdo e o título logo abaixo dele. O logo NÃO é escrito
  aqui — quem o desenha é `slide-top.vue`, em todo slide; o que a capa faz é
  reservar o espaço dele com `padding-top`.

  ---
  layout: capa
  kicker: Aula 01 · Psicologia
  subtitle: A pergunta que a aula responde.
  meta: 4 de setembro · turma da manhã
  ---

  `title` costuma vir do headmatter (no primeiro slide o bloco é headmatter e
  frontmatter ao mesmo tempo) — não repita o campo.
  `kicker`, `subtitle` e `meta` aceitam HTML.

  A capa não aceita imagem: o template do evento pede que ali estejam só a
  marca-d'água e o logotipo.
-->
<script setup lang="ts">
// `title` é campo reservado do Slidev: ele o usa para o índice e NÃO o repassa como prop.
// O jeito de lê-lo é pelo objeto `frontmatter`, que chega inteiro em todo layout.
// Ver docs/design-system.md → "Os campos que o Slidev não entrega".
const props = defineProps<{
  kicker?: string
  subtitle?: string
  meta?: string
  frontmatter?: Record<string, any>
}>()

const title = props.frontmatter?.title
</script>

<template>
  <div class="slidev-layout ds-capa">
    <div class="texto">
      <p v-if="kicker" class="ds-kicker" v-html="kicker" />
      <h1 v-if="title" v-html="title" />
      <div class="ds-rule" />
      <p v-if="subtitle" class="ds-lead" v-html="subtitle" />
      <div class="corpo"><slot /></div>
    </div>

    <p v-if="meta" class="meta ds-small" v-html="meta" />
  </div>
</template>

<style scoped>
/* Os dois paddings são as duas faixas que o texto não invade: em cima, o
   logotipo que `slide-top.vue` põe em 10,1%; embaixo, o `meta`, que é
   `absolute` e portanto não empurraria nada — sem esta reserva o bloco
   centralizado passa por cima dele. */
.ds-capa {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
  padding-top: 9rem;
  padding-bottom: 6rem;
}

/* A coluna do texto para antes da marca-d'água, que ocupa a faixa direita. */
.texto {
  max-width: 64%;
}

/* Um degrau abaixo do `3xl`: a coluna da capa tem 64% da largura do slide, e
   54px ali quebrariam o título em cinco linhas. */
.ds-capa :deep(h1) {
  margin: 0;
  padding: 0;
  font-size: 2.9rem;
  line-height: 1.06;
}

/* O fio de ouro embaixo do h1 é da regra geral de título de slide; na capa
   quem faz esse papel é a `.ds-rule`, que vem depois do título. */
.ds-capa :deep(h1::after) {
  display: none;
}

.ds-capa .ds-lead {
  max-width: 42ch;
  color: var(--ds-muted);
}

.corpo:not(:empty) {
  margin-top: var(--ds-space-5);
}

/* O rodapé para em 40%: a partir dali começa a marca-d'água. */
.meta {
  position: absolute;
  bottom: 1.9rem;
  left: 4.4rem;
  right: 40%;
  margin: 0;
  padding-top: var(--ds-space-3);
  border-top: var(--ds-border) solid var(--ds-rule);
}
</style>
