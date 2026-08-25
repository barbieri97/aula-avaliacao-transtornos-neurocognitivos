<!--
  roteiro — o índice da aula, ou qualquer lista curta de tópico + explicação.
  Repita o slide ao longo do deck com `atual:` diferente e a turma sempre sabe
  onde está.

  ---
  layout: roteiro
  kicker: Aula 01
  title: O caminho de hoje
  itens:
    - { tema: O que mudou no DSM-5, desc: de demência a transtorno neurocognitivo }
    - { tema: Os seis domínios, desc: o que se mede, e com o quê }
    - { tema: Leve ou maior, desc: onde está a linha }
  atual: 2
  ---

  Cada item aceita `tema` e `desc` (os dois com HTML). Um item pode ser só uma
  string, e aí vira o `tema` sem descrição. `atual: 2` marca onde a aula está.
-->
<script setup lang="ts">
// `title` chega pelo objeto `frontmatter`, não como prop — ver o comentário em capa.vue.
import Moldura from '../lib/Moldura.vue'

const props = defineProps<{
  kicker?: string
  itens?: (string | { tema?: string, desc?: string })[]
  atual?: number
  frontmatter?: Record<string, any>
}>()

const title = props.frontmatter?.title

// Aceita `- item` e `- { tema, desc }` na mesma lista: normaliza antes de renderizar.
const itensNormalizados = (props.itens ?? []).map(item =>
  typeof item === 'string' ? { tema: item, desc: '' } : item,
)
</script>

<template>
  <div class="slidev-layout ds-roteiro">
    <Moldura />
    <p v-if="kicker" class="ds-kicker" v-html="kicker" />
    <h1 v-if="title" v-html="title" />

    <ol class="lista">
      <li
        v-for="(item, i) in itensNormalizados"
        :key="i"
        :class="{ atual: atual === i + 1 }"
      >
        <span class="num ds-num">{{ String(i + 1).padStart(2, '0') }}</span>
        <span class="texto">
          <span class="tema" v-html="item.tema" />
          <span v-if="item.desc" class="desc" v-html="item.desc" />
        </span>
      </li>
    </ol>

    <slot />
  </div>
</template>

<style scoped>
.ds-roteiro {
  position: relative;
  height: 100%;
}

.lista {
  display: grid;
  gap: 0;
  margin: var(--ds-space-5) 0 0;
  padding: 0;
  max-width: none;
  list-style: none;
}

/* Um filete entre itens em vez de cartões: a lista é uma só coisa, não seis. */
.lista li {
  display: flex;
  align-items: baseline;
  gap: var(--ds-space-4);
  margin: 0;
  padding: var(--ds-space-3) var(--ds-space-4);
  border-top: var(--ds-border) solid var(--ds-rule);
  border-left: var(--ds-border-thick) solid transparent;
}

.lista li:last-child {
  border-bottom: var(--ds-border) solid var(--ds-rule);
}

/* O item da vez ganha a barra e a lavagem; os outros ficam de fora, não
   apagados — o roteiro serve para se localizar, não para esconder o resto. */
.lista li.atual {
  border-left-color: var(--ds-ouro);
  background: var(--ds-accent-wash);
}

.num {
  flex: none;
  color: var(--ds-accent-forte);
  font-size: var(--ds-text-xs);
  font-weight: 700;
  letter-spacing: 0.08em;
}

.texto {
  display: flex;
  align-items: baseline;
  gap: var(--ds-space-3);
  flex-wrap: wrap;
}

.tema {
  font-size: var(--ds-text-lg);
  font-weight: 600;
}

.desc {
  color: var(--ds-muted);
  font-size: var(--ds-text-base);
}
</style>
