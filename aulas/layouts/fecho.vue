<!--
  fecho — o último slide: o que fica e o que vem. Papel, como a capa,
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
  <div class="slidev-layout ds-fecho">
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
/* `justify-content: center` centralizaria o bloco verticalmente — mas com
   quatro pontos o bloco pode ficar mais alto que o slide, e centralizar
   faria o título sumir por cima tanto quanto o `proximo` é encostado por
   baixo. Começar do topo garante que, se sobrar conteúdo, ele sobra só
   embaixo — nunca por cima do título. */
.ds-fecho {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  height: 100%;
}

/* O texto para antes da faixa direita, que é da marca-d'água. */
.texto {
  max-width: 62%;
}

.ds-fecho :deep(h1) {
  margin: 0 0 var(--ds-space-5);
  font-size: var(--ds-text-2xl);
}

.pontos {
  display: grid;
  gap: 0;
  max-width: none;
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
  color: var(--ds-accent-forte);
  font-size: var(--ds-text-xs);
  font-weight: 700;
  letter-spacing: 0.08em;
}

.o-que {
  font-size: var(--ds-text-lg);
  line-height: var(--ds-leading-normal);
}

/* O rodapé para em 35% da direita: dali para lá é o canto do logotipo. */
.proximo {
  position: absolute;
  left: 4.4rem;
  right: 35%;
  bottom: 1.9rem;
  margin: 0;
  max-width: none;
  padding-left: var(--ds-space-4);
  border-left: var(--ds-border-thick) solid var(--ds-ouro);
  color: var(--ds-muted);
  font-size: var(--ds-text-sm);
  line-height: var(--ds-leading-normal);
}
</style>
