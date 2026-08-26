<!--
  <Fluxo> — etapas encadeadas, com a seta desenhada em SVG entre elas. É o
  esquema de processo: o que vem antes, o que vem depois, e onde a decisão
  acontece.

  <Fluxo :etapas="[
    { titulo: 'Queixa', desc: 'do paciente ou do informante' },
    { titulo: 'Rastreio', desc: 'MoCA, fluência, relógio' },
    { titulo: 'Testagem', desc: 'os seis domínios', cor: 'ouro' },
  ]" />

  `orientacao`: horizontal (padrão) · vertical — a vertical cabe mais texto por
  etapa; a horizontal mostra melhor que existe um sentido.
  `porLinha`: quantas etapas cabem numa fileira. Acima de cinco etapas na
  horizontal cada caixa fica com menos de 60px de texto útil — aí `porLinha`
  quebra o fluxo em fileiras, que se leem como texto: da esquerda para a
  direita, de cima para baixo.
  `cor` de cada etapa: nenhuma (padrão) · azul · ouro · verde · terra · cinza.
-->
<script setup lang="ts">
import { computed } from 'vue'

type Etapa = { titulo?: string, desc?: string, cor?: string }

const props = withDefaults(defineProps<{
  etapas?: Etapa[]
  orientacao?: 'horizontal' | 'vertical'
  porLinha?: number
}>(), { orientacao: 'horizontal' })

// Uma fileira só é o padrão; `porLinha` fatia a lista em várias. A seta é
// desenhada DENTRO da fileira, entre duas etapas — nunca no fim dela, que é
// onde a leitura vira a linha sozinha.
const fileiras = computed<Etapa[][]>(() => {
  const etapas = props.etapas ?? []
  const n = props.porLinha
  if (!n || n < 1 || etapas.length <= n) return [etapas]
  const saida: Etapa[][] = []
  for (let i = 0; i < etapas.length; i += n) saida.push(etapas.slice(i, i + n))
  return saida
})

// Sete etapas em fileiras de quatro deixam a segunda com três — e três caixas
// dividindo a mesma largura ficam mais gordas que as quatro de cima, o que faz
// a fileira de baixo parecer outra coisa. As vagas que faltam entram como
// caixas invisíveis, e as duas fileiras voltam a ter a mesma medida.
const vagasVazias = computed(() => {
  const n = props.porLinha ?? 0
  const ultima = fileiras.value[fileiras.value.length - 1]
  if (fileiras.value.length < 2 || !ultima) return 0
  return Math.max(0, n - ultima.length)
})
</script>

<template>
  <div class="ds-fluxo" :class="[orientacao, { fileirado: fileiras.length > 1 }]">
    <div v-for="(fileira, f) in fileiras" :key="f" class="fileira">
      <template v-for="(etapa, i) in fileira" :key="i">
        <div class="etapa" :class="`cor-${etapa.cor ?? 'nenhuma'}`">
          <span class="titulo" v-html="etapa.titulo" />
          <span v-if="etapa.desc" class="desc" v-html="etapa.desc" />
        </div>

        <svg
          v-if="i < fileira.length - 1"
          class="seta"
          viewBox="0 0 32 24"
          aria-hidden="true"
        >
          <path d="M3 12 H23" />
          <path d="M19 6.5 L26 12 L19 17.5" />
        </svg>
      </template>

      <template v-if="f === fileiras.length - 1">
        <template v-for="v in vagasVazias" :key="`vaga-${v}`">
          <span class="seta" aria-hidden="true" />
          <div class="etapa vaga" aria-hidden="true" />
        </template>
      </template>
    </div>
  </div>
</template>

<style scoped>
.ds-fluxo {
  display: flex;
  flex-direction: column;
  gap: var(--ds-space-4);
  margin: var(--ds-space-4) 0;
}

.fileira {
  display: flex;
  align-items: stretch;
  gap: var(--ds-space-2);
}

.ds-fluxo.vertical .fileira {
  flex-direction: column;
  align-items: stretch;
}

/* Alinhado pelo topo, e não centrado: com descrições de tamanhos diferentes,
   centrar deixa os títulos das etapas em alturas diferentes — e o olho lê a
   fileira como se fossem coisas de níveis diferentes. */
.etapa {
  display: flex;
  flex-direction: column;
  gap: var(--ds-space-1);
  justify-content: flex-start;
  flex: 1;
  min-width: 0;
  padding: var(--ds-space-3) var(--ds-space-4);
  border: var(--ds-border) solid var(--ds-rule-forte);
  background: var(--ds-surface);
}

/* Cinco etapas na horizontal deixam pouco mais de 7rem por caixa: o título
   entra no corpo base, e `overflow-wrap` garante que uma palavra comprida
   quebre em vez de vazar por cima da etapa vizinha. */
.titulo {
  font-family: var(--ds-font-serif);
  font-size: var(--ds-text-base);
  font-weight: 600;
  line-height: var(--ds-leading-tight);
  overflow-wrap: anywhere;
}

.ds-fluxo.vertical .titulo {
  font-size: var(--ds-text-lg);
}

/* Fileira quebrada tem espaço de sobra por caixa — mas o título fica no corpo
   base mesmo assim: a 23px, "Comorbidades" não cabe numa caixa de quatro por
   fileira e o `overflow-wrap` a parte no meio. Quem cresce é a descrição. */

.desc {
  color: var(--ds-muted);
  font-size: var(--ds-text-xs);
  line-height: var(--ds-leading-normal);
}

.ds-fluxo.fileirado .desc {
  font-size: var(--ds-text-sm);
}

/* A seta é um SVG de traço, não um caractere: assim ela tem a mesma espessura
   dos fios do deck e não depende de fonte para aparecer no PDF. */
.seta {
  flex: none;
  align-self: center;
  width: 2rem;
  height: 1.5rem;
  fill: none;
  stroke: var(--ds-ouro);
  stroke-width: 2;
  stroke-linecap: round;
  stroke-linejoin: round;
}

.ds-fluxo.vertical .seta {
  transform: rotate(90deg);
}

/* A vaga ocupa o lugar de uma etapa que não existe: mesma medida, nada
   desenhado. */
.etapa.vaga {
  border-color: transparent;
  background: transparent;
}

.cor-azul { border-color: transparent; background: var(--ds-pastel-azul); }
.cor-ouro { border-color: transparent; background: var(--ds-pastel-ouro); }
.cor-verde { border-color: transparent; background: var(--ds-pastel-verde); }
.cor-terra { border-color: transparent; background: var(--ds-pastel-terra); }
.cor-cinza { border-color: transparent; background: var(--ds-pastel-cinza); }
</style>
