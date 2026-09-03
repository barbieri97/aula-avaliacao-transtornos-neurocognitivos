<!--
  comparacao — a tabela de diferencial, que é o que a aula clínica mais faz:
  duas ou três coisas parecidas, linha a linha, no mesmo critério.

  ---
  layout: comparacao
  title: Três quadros que se confundem
  colunas:
    - { titulo: Delirium, sub: agudo, cor: terra }
    - { titulo: TNC maior, sub: crônico, cor: azul }
    - { titulo: Depressão, sub: subagudo, cor: verde }
  linhas:
    - { criterio: Início, valores: [horas a dias, meses a anos, semanas] }
    - { criterio: Atenção, valores: [flutuante, preservada no início, variável] }
  ---

  `cor` de cada coluna: azul (padrão) · ouro · verde · terra · cinza. Todo texto
  aceita HTML. Três colunas é o teto — na quarta ninguém lê a linha inteira.
-->
<script setup lang="ts">
// `title` chega pelo objeto `frontmatter`, não como prop — ver o comentário em capa.vue.
import Moldura from '../lib/Moldura.vue'

const props = defineProps<{
  colunas?: { titulo?: string, sub?: string, cor?: 'azul' | 'ouro' | 'verde' | 'terra' | 'cinza' }[]
  linhas?: { criterio?: string, valores?: string[] }[]
  frontmatter?: Record<string, any>
}>()

const title = props.frontmatter?.title
const colunas = props.colunas ?? []
</script>

<template>
  <div class="slidev-layout ds-comparacao">
    <Moldura />
    <h1 v-if="title" v-html="title" />

    <div class="tabela-caixa">
      <div
        class="tabela"
        :style="{ '--ds-colunas': colunas.length }"
      >
        <div class="linha cabecalho">
          <div class="celula criterio" />
          <div
            v-for="(coluna, c) in colunas"
            :key="c"
            class="celula titulo"
            :class="`cor-${coluna.cor ?? 'azul'}`"
          >
            <span class="nome" v-html="coluna.titulo" />
            <span v-if="coluna.sub" class="sub" v-html="coluna.sub" />
          </div>
        </div>

        <div v-for="(linha, i) in linhas" :key="i" class="linha">
          <div class="celula criterio" v-html="linha.criterio" />
          <div
            v-for="(coluna, c) in colunas"
            :key="c"
            class="celula valor"
            :class="`cor-${coluna.cor ?? 'azul'}`"
            v-html="linha.valores?.[c] ?? ''"
          />
        </div>
      </div>
    </div>

    <slot />
  </div>
</template>

<style scoped>
.ds-comparacao {
  position: relative;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.ds-comparacao :deep(h1) {
  flex: none;
}

/* A tabela começa logo abaixo do título: com quatro linhas (ou um slot
   depois dela), centralizar faria a tabela crescer para cima e encostar
   no título — melhor sobrar espaço embaixo do que sobrepor o de cima. */
.tabela-caixa {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  flex: 1;
  min-height: 0;
}

/* Grid de verdade, e não <table>: a coluna inteira pode ser pintada sem
   repetir a cor em cada célula, e as linhas alinham mesmo com texto de
   alturas diferentes. */
.tabela {
  display: grid;
  grid-template-columns: 9.5rem repeat(var(--ds-colunas, 2), minmax(0, 1fr));
  margin-top: var(--ds-space-2);
}

.linha {
  display: contents;
}

/* `min-width: 0` e `overflow-wrap` são o par que segura uma palavra sem
   espaço — "Neurodesenvolvimento" numa coluna de três: sem eles a célula
   cresce além do `1fr` e o texto vaza por cima da coluna vizinha. Onde a
   quebra tem lugar certo, escreva um `&shy;` no próprio texto. */
.celula {
  min-width: 0;
  padding: var(--ds-space-3) var(--ds-space-4);
  border-top: var(--ds-border) solid var(--ds-rule);
  font-size: var(--ds-text-sm);
  line-height: var(--ds-leading-normal);
  overflow-wrap: break-word;
}

.cabecalho .celula {
  border-top: 0;
}

.criterio {
  padding-left: 0;
  color: var(--ds-muted);
  font-size: var(--ds-text-xs);
  font-weight: 700;
  letter-spacing: 0.04em;
  text-transform: uppercase;
}

.titulo {
  display: flex;
  flex-direction: column;
  gap: 0.1rem;
  padding-top: var(--ds-space-2);
  padding-bottom: var(--ds-space-3);
  border-bottom: 2px solid var(--ds-marinho);
}

.nome {
  font-family: var(--ds-font-serif);
  font-size: var(--ds-text-lg);
  font-weight: 600;
  line-height: var(--ds-leading-tight);
  overflow-wrap: break-word;
  hyphens: auto;
}

.sub {
  color: var(--ds-muted);
  font-size: var(--ds-text-xs);
  letter-spacing: 0.04em;
  text-transform: uppercase;
}

/* A lavagem pastel corre pela coluna toda: é ela que amarra o cabeçalho aos
   valores sem precisar de bordas verticais. */
.cor-azul {
  background: var(--ds-pastel-azul);
}

.cor-ouro {
  background: var(--ds-pastel-ouro);
}

.cor-verde {
  background: var(--ds-pastel-verde);
}

.cor-terra {
  background: var(--ds-pastel-terra);
}

.cor-cinza {
  background: var(--ds-pastel-cinza);
}
</style>
