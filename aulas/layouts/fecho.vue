<!--
  fecho — o último slide: o que fica e o que vem. Fundo marinho, como a capa,
  fechando o deck do jeito que ele abriu.

  ---
  layout: fecho
  kicker: Para levar
  title: Três coisas que ficam
  pontos:
    - Rastreio positivo não é diagnóstico.
    - Escolaridade muda o ponto de corte, não a régua.
    - Sem informante e sem funcionalidade, não há síndrome.
  proximo: Na próxima aula, os perfis das principais etiologias.
  ---

  Cada ponto aceita HTML. `proximo` é a faixa de rodapé.
-->
<script setup lang="ts">
// `title` chega pelo objeto `frontmatter`, não como prop — ver o comentário em capa.vue.
const props = defineProps<{
  kicker?: string
  pontos?: string[]
  proximo?: string
  frontmatter?: Record<string, any>
}>()

const title = props.frontmatter?.title
</script>

<template>
  <div class="slidev-layout ds-fecho ds-inverso">
    <div class="texto">
      <p v-if="kicker" class="ds-kicker" v-html="kicker" />
      <h1 v-if="title" v-html="title" />

      <ol v-if="pontos?.length" class="pontos">
        <li v-for="(ponto, i) in pontos" :key="i">
          <span class="num ds-num">{{ String(i + 1).padStart(2, '0') }}</span>
          <span class="o-que" v-html="ponto" />
        </li>
      </ol>

      <slot />
    </div>

    <p v-if="proximo" class="proximo" v-html="proximo" />
  </div>
</template>

<style scoped>
.ds-fecho {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
}

.ds-fecho :deep(h1) {
  margin: 0 0 var(--ds-space-5);
  font-size: var(--ds-text-2xl);
}

.pontos {
  display: grid;
  gap: 0;
  max-width: 46rem;
  margin: 0;
  padding: 0;
  list-style: none;
}

.pontos li {
  display: flex;
  align-items: baseline;
  gap: var(--ds-space-4);
  margin: 0;
  padding: var(--ds-space-4) 0;
  border-top: var(--ds-border) solid var(--ds-rule);
}

.pontos li:last-child {
  border-bottom: var(--ds-border) solid var(--ds-rule);
}

.num {
  flex: none;
  color: var(--ds-ouro-luz);
  font-size: var(--ds-text-xs);
  font-weight: 700;
  letter-spacing: 0.08em;
}

.o-que {
  font-size: var(--ds-text-lg);
  line-height: var(--ds-leading-normal);
}

.proximo {
  position: absolute;
  left: 4.4rem;
  right: 3.2rem;
  bottom: 1.9rem;
  margin: 0;
  max-width: none;
  padding-left: var(--ds-space-4);
  border-left: var(--ds-border-thick) solid var(--ds-ouro-luz);
  color: var(--ds-muted);
  font-size: var(--ds-text-sm);
  line-height: var(--ds-leading-normal);
}
</style>
