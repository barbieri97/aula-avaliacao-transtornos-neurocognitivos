<!--
  <Continuum> — a faixa que mostra que duas categorias são dois pontos de uma
  linha, e não duas caixas. Serve para gravidade, para tempo, para qualquer
  gradiente que a aula não queira que a turma leia como dicotomia.

  <Continuum :marcos="[
    { rotulo: 'Cognição típica', nota: 'acima de −1 DP' },
    { rotulo: 'TNC leve', nota: 'entre −1 e −2 DP', destaque: true },
    { rotulo: 'TNC maior', nota: 'abaixo de −2 DP' },
  ]" />

  A cor de cada faixa segue a ordem verde → ouro → terra, e pode ser fixada em
  `cor`. `rotulo` e `nota` aceitam HTML. Quatro marcos é o teto.
-->
<script setup lang="ts">
const props = defineProps<{
  marcos?: { rotulo?: string, nota?: string, cor?: string, destaque?: boolean }[]
}>()

const SEQUENCIA = ['verde', 'ouro', 'terra', 'azul']
const marcos = (props.marcos ?? []).map((marco, i) => ({
  ...marco,
  cor: marco.cor ?? SEQUENCIA[i % SEQUENCIA.length],
}))

// A faixa é desenhada num sistema de 1000 unidades de largura: as divisões e a
// ponta da seta são calculadas aqui para o SVG e reaproveitadas, em `flex: 1`,
// pelos rótulos em HTML logo abaixo.
const LARGURA = 1000
const PONTA = 46
const passo = (LARGURA - PONTA) / Math.max(marcos.length, 1)
const faixas = marcos.map((marco, i) => ({
  cor: marco.cor,
  x: i * passo,
  largura: passo,
  ultima: i === marcos.length - 1,
}))
</script>

<template>
  <div class="ds-continuum">
    <svg class="faixa" viewBox="0 0 1000 30" preserveAspectRatio="none" aria-hidden="true">
      <rect
        v-for="(faixa, i) in faixas"
        :key="i"
        :x="faixa.x"
        :width="faixa.largura + (faixa.ultima ? 0 : 0.5)"
        y="6"
        height="18"
        :class="`cor-${faixa.cor}`"
      />
      <!-- O fio embaixo de cada faixa: o pastel sozinho some no projetor. -->
      <rect
        v-for="(faixa, i) in faixas"
        :key="`fio-${i}`"
        :x="faixa.x"
        :width="faixa.largura"
        y="24"
        height="3"
        :class="`fio-${faixa.cor}`"
      />
      <!-- A ponta fecha a faixa: é ela que diz que a linha continua. -->
      <path
        :d="`M ${LARGURA - PONTA} 0 L ${LARGURA} 15 L ${LARGURA - PONTA} 30 Z`"
        :class="`cor-${faixas[faixas.length - 1]?.cor}`"
      />
    </svg>

    <ul class="rotulos">
      <li v-for="(marco, i) in marcos" :key="i" :class="{ destaque: marco.destaque }">
        <span class="tique" />
        <span class="rotulo" v-html="marco.rotulo" />
        <span v-if="marco.nota" class="nota" v-html="marco.nota" />
      </li>
    </ul>
  </div>
</template>

<style scoped>
.ds-continuum {
  margin: var(--ds-space-4) 0;
}

/* `preserveAspectRatio: none` é de propósito: a faixa é só um retângulo com
   uma ponta, e esticar horizontalmente é exatamente o que se quer dela. */
.faixa {
  display: block;
  width: 100%;
  height: 1.6rem;
}

.rotulos {
  display: flex;
  margin: 0;
  padding: 0;
  max-width: none;
  list-style: none;
}

.rotulos li {
  display: flex;
  flex-direction: column;
  gap: 0.1rem;
  flex: 1;
  margin: 0;
  padding: var(--ds-space-3) var(--ds-space-3) 0 0;
}

.rotulos li::before {
  content: none;
}

/* O tique amarra o rótulo ao começo da sua faixa — sem ele o olho não sabe se
   o texto se refere ao trecho da esquerda ou ao da direita. */
.tique {
  width: 1px;
  height: var(--ds-space-3);
  margin-top: calc(-1 * var(--ds-space-3));
  background: var(--ds-rule-forte);
}

.rotulo {
  margin-top: var(--ds-space-1);
  font-size: var(--ds-text-base);
  font-weight: 600;
  line-height: var(--ds-leading-tight);
}

.nota {
  color: var(--ds-muted);
  font-size: var(--ds-text-xs);
}

.rotulos li.destaque .tique {
  width: 3px;
  background: var(--ds-marinho);
}

.rotulos li.destaque .rotulo {
  color: var(--ds-ink);
}

.rotulos li.destaque .nota {
  color: var(--ds-accent-forte);
  font-weight: 600;
}

.fio-verde { fill: var(--ds-ok); }
.fio-ouro { fill: var(--ds-warn); }
.fio-terra { fill: var(--ds-danger); }
.fio-azul { fill: var(--ds-marinho); }

.cor-verde { fill: var(--ds-pastel-verde); }
.cor-ouro { fill: var(--ds-pastel-ouro); }
.cor-terra { fill: var(--ds-pastel-terra); }
.cor-azul { fill: var(--ds-pastel-azul); }
</style>
