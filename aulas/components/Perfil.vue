<!--
  <Perfil> — o gráfico de perfil cognitivo: um domínio por linha, o escore
  padronizado (z) como barra que sai da média. É o desenho que a aula clínica
  mais usa, e o que mostra de uma vez que avaliação não produz UM número.

  <Perfil :dominios="[
    { nome: 'Atenção complexa', z: -0.4 },
    { nome: 'Função executiva', z: -1.6 },
    { nome: 'Memória', z: -2.4 },
  ]" />

  A cor da barra é lida do próprio escore, e é aí que o esquema ensina:
  até −1 DP dentro do esperado (verde), entre −1 e −2 limítrofe (âmbar),
  abaixo de −2 rebaixado (vermelho). Ponha uma <Legenda> embaixo dizendo isso.

  `min` e `max` mudam o eixo (padrão: −3 a +1,5 desvios-padrão).
-->
<script setup lang="ts">
const props = withDefaults(defineProps<{
  dominios?: { nome?: string, z?: number }[]
  min?: number
  max?: number
}>(), { min: -3, max: 1.5 })

// O desenho é feito num sistema de coordenadas de 760 unidades de largura, que
// é mais ou menos a largura em pixels que o esquema ocupa num slide: assim os
// tamanhos de texto do SVG batem com os do resto do deck, em vez de encolherem
// junto com a escala.
const LARGURA = 760
const X0 = 234 // onde começa a área do gráfico (à esquerda ficam os nomes)
const X1 = 748
const TOPO = 30 // espaço para a régua de desvios-padrão
const LINHA = 36
const BARRA = 18

const dominios = props.dominios ?? []
const altura = TOPO + dominios.length * LINHA + 6

const x = (z: number) => X0 + ((z - props.min) / (props.max - props.min)) * (X1 - X0)
const yCentro = (i: number) => TOPO + i * LINHA + LINHA / 2

/** Os inteiros dentro do eixo — a régua de desvios-padrão. */
const tiques = Array.from(
  { length: Math.floor(props.max) - Math.ceil(props.min) + 1 },
  (_, i) => Math.ceil(props.min) + i,
)

/** −2,4 → "−2,4". Sinal de menos de verdade (−), vírgula decimal. */
const formatar = (z: number) => `${z < 0 ? '−' : '+'}${Math.abs(z).toFixed(1).replace('.', ',')}`

const faixaDe = (z: number) => (z >= -1 ? 'ok' : z > -2 ? 'warn' : 'danger')

const barras = dominios.map((dominio, i) => {
  const z = dominio.z ?? 0
  const xz = x(z)
  const zero = x(0)
  return {
    nome: dominio.nome,
    rotulo: formatar(z),
    faixa: faixaDe(z),
    y: yCentro(i) - BARRA / 2,
    yTexto: yCentro(i),
    xBarra: Math.min(xz, zero),
    largura: Math.max(Math.abs(xz - zero), 2),
    xRotulo: z < 0 ? xz - 10 : xz + 10,
    ancora: z < 0 ? 'end' : 'start',
  }
})
</script>

<template>
  <svg class="ds-perfil" :viewBox="`0 0 ${LARGURA} ${altura}`" role="img">
    <!-- A faixa do esperado entra antes de tudo: é o fundo contra o qual se lê
         cada barra, não mais um elemento por cima. -->
    <rect class="banda" :x="x(-1)" :width="X1 - x(-1)" :y="TOPO - 6" :height="altura - TOPO" />

    <g class="regua">
      <template v-for="tique in tiques" :key="tique">
        <line :x1="x(tique)" :x2="x(tique)" :y1="TOPO - 6" :y2="altura - 6" />
        <text :x="x(tique)" :y="TOPO - 14" text-anchor="middle">{{ tique > 0 ? `+${tique}` : tique === 0 ? '0' : `−${Math.abs(tique)}` }}</text>
      </template>
    </g>

    <line class="zero" :x1="x(0)" :x2="x(0)" :y1="TOPO - 6" :y2="altura - 6" />

    <g v-for="(barra, i) in barras" :key="i">
      <text class="nome" :x="X0 - 14" :y="barra.yTexto" text-anchor="end" dominant-baseline="middle">{{ barra.nome }}</text>
      <rect class="barra" :class="barra.faixa" :x="barra.xBarra" :y="barra.y" :width="barra.largura" :height="BARRA" />
      <text class="valor" :class="barra.faixa" :x="barra.xRotulo" :y="barra.yTexto" :text-anchor="barra.ancora" dominant-baseline="middle">{{ barra.rotulo }}</text>
    </g>
  </svg>
</template>

<style scoped>
/* Nenhuma cor escrita à mão: o SVG usa classe e a classe lê o token, igual ao
   resto do design system. */
.ds-perfil {
  display: block;
  width: 100%;
  height: auto;
  margin: var(--ds-space-3) 0;
  font-family: var(--ds-font-sans);
}

.banda {
  fill: var(--ds-pastel-verde);
}

.regua line {
  stroke: var(--ds-rule-forte);
  stroke-width: 1;
  stroke-dasharray: 2 4;
}

.regua text {
  fill: var(--ds-muted);
  font-size: 15px;
  font-variant-numeric: tabular-nums;
}

.zero {
  stroke: var(--ds-marinho);
  stroke-width: 2;
}

.nome {
  fill: var(--ds-ink);
  font-size: 16px;
}

.barra.ok { fill: var(--ds-ok); }
.barra.warn { fill: var(--ds-warn); }
.barra.danger { fill: var(--ds-danger); }

.valor {
  font-size: 15px;
  font-weight: 700;
  font-variant-numeric: tabular-nums;
}

.valor.ok { fill: var(--ds-ok); }
.valor.warn { fill: var(--ds-warn); }
.valor.danger { fill: var(--ds-danger); }
</style>
