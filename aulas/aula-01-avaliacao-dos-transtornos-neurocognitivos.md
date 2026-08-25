---
theme: none
title: Avaliação dos transtornos neurocognitivos
info: Do rastreio ao diagnóstico sindrômico — o que a testagem responde e o que ela não responde
date: "2026-09-03"
colorSchema: light
layout: capa
kicker: Aula 01 · Psicologia
subtitle: Do rastreio ao diagnóstico sindrômico — e do escore à pessoa que fez o teste.
imagem: /capa-perfil.svg
meta: "2 horas · leitura prévia: DSM-5-TR, capítulo de transtornos neurocognitivos"
---

<!--
Abrir perguntando quantos já acompanharam alguém com queixa de memória na família.
A aula inteira responde a uma pergunta prática: quando a queixa vira hipótese, e quando a
hipótese vira síndrome.
-->

---
layout: roteiro
kicker: Aula 01
title: O caminho de hoje
itens:
  - { tema: O que mudou de nome, desc: e o que mudou de fato }
  - { tema: Os seis domínios, desc: o que se mede, e com o quê }
  - { tema: Leve ou maior, desc: onde exatamente está a linha }
  - { tema: O caso, desc: a conduta diante de um perfil real }
---

---
layout: destaque
kicker: A tese da aula
title: Avaliar não é medir. É comparar alguém com <span class="ds-grifo">quem ele era</span>.
fonte: O nível prévio de desempenho é a única linha de base que interessa — e ela nunca está na tabela normativa.
---

<!--
Deixar a frase na tela em silêncio por alguns segundos. Perguntar: como se estima o nível
prévio de alguém que você conheceu hoje? Respostas esperadas: escolaridade, ocupação,
relato de informante, leitura e escrita. É o gancho do bloco 1.
-->

---
layout: secao
numero: "01"
kicker: Parte 1
title: O que mudou de nome — e o que mudou de fato
note: Demência saiu do manual. O que entrou no lugar não é um sinônimo mais educado.
---

---
layout: default
---

# Do caso de Auguste D. ao DSM-5-TR

<LinhaDoTempo :itens="[
  { quando: '1907', o_que: 'Alois Alzheimer', desc: 'descreve o caso de Auguste D. e a alteração histopatológica' },
  { quando: '1999', o_que: 'Comprometimento cognitivo leve', desc: 'Petersen delimita o estado entre o envelhecimento típico e a demência' },
  { quando: '2013', o_que: 'DSM-5', desc: 'demência vira <b>transtorno neurocognitivo maior</b>; o CCL vira <b>leve</b>' },
  { quando: '2022', o_que: 'DSM-5-TR', desc: 'mantém a estrutura e revisa a nomenclatura das etiologias' },
]" />

<Fonte>American Psychiatric Association, <em>DSM-5-TR</em>, 2022 · Petersen et al., <em>Archives of Neurology</em>, 1999.</Fonte>

<!--
O ponto histórico que interessa: a mudança de 2013 não foi cosmética. Ela tirou a memória do
centro obrigatório do diagnóstico e pôs a funcionalidade como o divisor entre leve e maior.
-->

---
layout: default
---

# O que o nome novo diz

<Termo palavra="Transtorno neurocognitivo" origem="DSM-5-TR, 2022">

Declínio **adquirido** em um ou mais domínios cognitivos, em relação a um nível prévio de
desempenho, documentado por relato **e** por medida objetiva.

</Termo>

<Nota titulo="Três palavras fazem trabalho">

**Adquirido** exclui o que sempre foi assim. **Em relação a um nível prévio** exclui o escore
baixo de quem nunca pontuou alto. **E** exige as duas coisas: queixa sem medida é queixa;
medida sem queixa é escore.

</Nota>

---
layout: esquema
title: Leve e maior são dois pontos de uma linha
legenda: A linha é contínua; o corte é uma convenção clínica — que existe porque a conduta muda de um lado para o outro.
---

<Continuum :marcos="[
  { rotulo: 'Cognição típica', nota: 'acima de −1 DP' },
  { rotulo: 'TNC leve', nota: 'entre −1 e −2 DP · independência preservada', destaque: true },
  { rotulo: 'TNC maior', nota: 'abaixo de −2 DP · independência perdida' },
]" />

<Legenda :itens="[
  { cor: 'verde', texto: 'dentro do esperado para idade e escolaridade' },
  { cor: 'ouro', texto: 'declínio modesto, com esforço compensatório' },
  { cor: 'terra', texto: 'declínio substancial, com perda funcional' },
]" />

<!--
Insistir: a passagem de leve para maior não é um novo transtorno, é o mesmo continuum. O que
o clínico observa mudar primeiro é a funcionalidade, não o escore.
-->

---
layout: comparacao
title: Onde exatamente está a linha
colunas:
  - { titulo: TNC leve, sub: modesto, cor: ouro }
  - { titulo: TNC maior, sub: substancial, cor: terra }
linhas:
  - { criterio: Escore, valores: ["entre −1 e −2 DP (percentil 3 a 16)", "abaixo de −2 DP (percentil ≤ 3)"] }
  - { criterio: Independência, valores: ["preservada, com mais esforço ou estratégia", "perdida nas atividades instrumentais"] }
  - { criterio: Exemplo, valores: ["passa a anotar tudo o que antes lembrava", "erra a dose do próprio remédio"] }
  - { criterio: Conduta, valores: ["monitorar, tratar o tratável, reavaliar", "investigar etiologia e organizar suporte"] }
---

<!--
A linha de "Exemplo" é a que a turma leva embora. Perguntar por outros exemplos do cotidiano
de cada um antes de avançar.
-->

---
layout: pergunta
kicker: Antes de continuar
title: O escore caiu. Por que <em>ainda</em> não é diagnóstico?
pistas:
  - O que mais derruba um escore além de doença?
  - Quem confirma que houve mudança?
---

<v-click>

Porque um escore baixo tem muitas causas antes da neurodegeneração:
<span v-mark="{ at: 2, type: 'underline', class: 'ds-marca-ouro' }">escolaridade</span>,
<span v-mark="{ at: 2, type: 'underline', class: 'ds-marca-ouro' }">depressão</span>,
<span v-mark="{ at: 2, type: 'underline', class: 'ds-marca-ouro' }">medicação</span>,
déficit sensorial não corrigido, dor, insônia, o dia que a pessoa teve.

**Diagnóstico é a comparação com o nível prévio** — e essa comparação depende de história
clínica e de informante, não do teste.

</v-click>

---
layout: secao
numero: "02"
kicker: Parte 2
title: Os seis domínios
note: O manual não pede "memória". Pede um mapa — e o mapa tem seis regiões.
---

---
layout: default
---

# O que se mede

<Grade :cols="3">

<Cartao rotulo="domínio 1" titulo="Atenção complexa" cor="azul">

Sustentada, dividida, seletiva. Velocidade de processamento.

</Cartao>

<Cartao rotulo="domínio 2" titulo="Função executiva" cor="azul">

Planejamento, flexibilidade, inibição, memória operacional.

</Cartao>

<Cartao rotulo="domínio 3" titulo="Aprendizagem e memória" cor="azul">

Evocação livre, com pista e reconhecimento — nessa ordem.

</Cartao>

<Cartao rotulo="domínio 4" titulo="Linguagem" cor="azul">

Nomeação, fluência, gramática, compreensão.

</Cartao>

<Cartao rotulo="domínio 5" titulo="Perceptomotor" cor="azul">

Construção visual, praxia, percepção, gnosia.

</Cartao>

<Cartao rotulo="domínio 6" titulo="Cognição social" cor="azul">

Reconhecimento de emoções, teoria da mente, adequação social.

</Cartao>

</Grade>

<!--
Perguntar qual domínio a turma acha que é o mais esquecido na prática. Resposta: cognição
social — e é justamente o que muda primeiro na variante comportamental da DFT.
-->

---
layout: esquema
title: Um perfil, não um número
legenda: O mesmo paciente, seis medidas. É a forma do perfil — e não a média dela — que aponta para uma hipótese etiológica.
---

<Perfil :dominios="[
  { nome: 'Atenção complexa', z: -0.4 },
  { nome: 'Função executiva', z: -1.7 },
  { nome: 'Aprendizagem e memória', z: -2.6 },
  { nome: 'Linguagem', z: -0.8 },
  { nome: 'Perceptomotor', z: -1.2 },
  { nome: 'Cognição social', z: -0.3 },
]" />

<Legenda :itens="[
  { cor: 'ok', texto: 'dentro do esperado (até −1 DP)' },
  { cor: 'warn', texto: 'limítrofe (−1 a −2 DP)' },
  { cor: 'danger', texto: 'rebaixado (abaixo de −2 DP)' },
]" />

<!--
Pedir que a turma leia o perfil em voz alta antes de qualquer comentário. O padrão amnéstico
com executivas limítrofes é o mais comum na doença de Alzheimer típica — mas isso é hipótese,
não conclusão, e é exatamente o que o próximo bloco discute.
-->

---
layout: figura
imagem: /curva-normal.svg
legenda: A área abaixo de −2 DP é <b>2%</b> da população. Duas em cada cem pessoas saudáveis pontuam ali — por definição.
lado: direita
---

# A régua é uma distribuição

Um escore só existe **contra uma norma**: idade, escolaridade, às vezes sexo e região.

Trocar a norma muda o diagnóstico sem que nada mude no paciente.

<Nota tipo="alerta" titulo="No Brasil isso não é detalhe">

O ponto de corte do MEEM varia de 20 a 29 pontos conforme os anos de estudo. Usar o corte
americano em quem estudou quatro anos produz diagnóstico onde não há doença.

</Nota>

<Fonte>Brucki et al., <em>Arquivos de Neuro-Psiquiatria</em>, 2003.</Fonte>

---
layout: figura
imagem: /teste-do-relogio.svg
legenda: 'Teste do desenho do relógio, dois protocolos do mesmo comando: "desenhe um relógio marcando 11h10".'
lado: esquerda
ajuste: contain
---

# O que um desenho mostra

O relógio é barato, rápido e **não é um teste de memória**: ele lê planejamento,
representação espacial e monitoramento.

Um escore único esconde isso. O protocolo, não.

<Nota titulo="Por que guardar o protocolo">

O desenho é o dado bruto. Dois pacientes com a mesma pontuação erram de maneiras diferentes —
e a maneira é o que sugere a etiologia.

</Nota>

---
layout: secao
numero: "03"
kicker: Parte 3
title: Do rastreio ao diagnóstico
note: Nenhum instrumento diagnostica sozinho. A sequência é que sustenta a conclusão.
---

---
layout: esquema
title: A sequência
legenda: Cada seta é uma decisão clínica, não uma etapa obrigatória — e o caminho volta atrás sempre que um achado clínico muda a hipótese.
---

<Fluxo :etapas="[
  { titulo: 'Queixa', desc: 'do próprio, do informante ou do clínico' },
  { titulo: 'Rastreio', desc: 'MoCA, fluência verbal, relógio' },
  { titulo: 'Testagem', desc: 'os seis domínios, com norma adequada', cor: 'ouro' },
  { titulo: 'Impacto', desc: 'informante, AIVDs, escalas' },
  { titulo: 'Síndrome', desc: 'leve ou maior — e só então a etiologia' },
]" />

<Nota tipo="erro" titulo="O atalho que invalida tudo">

Rastreio positivo não é diagnóstico. Rastreio negativo, em quem tem queixa e alta reserva
cognitiva, também não descarta.

</Nota>

---
layout: default
---

# Os critérios, na íntegra

<Criterios :itens="[
  { titulo: 'Declínio cognitivo substancial', texto: 'Preocupação do próprio, de informante ou do clínico <b>e</b> prejuízo documentado, de preferência por teste padronizado.' },
  { titulo: 'Interferência na independência', texto: 'No mínimo, exige auxílio em atividades instrumentais complexas — medicação, dinheiro, transporte.' },
  { titulo: 'Fora do delirium', texto: 'Os déficits não ocorrem exclusivamente durante um episódio de delirium.' },
  { titulo: 'Sem explicação melhor', texto: 'Não são mais bem explicados por outro transtorno mental — depressão maior e esquizofrenia à frente da fila.' },
]" />

<Fonte>Critérios do transtorno neurocognitivo <b>maior</b>. No <b>leve</b>, o critério B se inverte: a independência é preservada. APA, <em>DSM-5-TR</em>, 2022.</Fonte>

---
layout: caso
rotulo: Caso clínico
title: Sr. J., 72 anos
dados:
  - { campo: Escolaridade, valor: 4 anos }
  - { campo: Ocupação, valor: marceneiro aposentado }
  - { campo: Queixa, valor: "esquece recados; a filha insiste, ele minimiza", destaque: true }
  - { campo: Evolução, valor: "2 anos, lenta e contínua" }
  - { campo: Rastreio, valor: "MEEM 24 · relógio irregular" }
  - { campo: Comorbidades, valor: "HAS, hipotireoidismo" }
---

## Antes de interpretar o escore, três decisões

1. Qual norma se aplica a **quatro anos de estudo**?
2. O que a filha responde que ele não responde?
3. O que precisa ser descartado antes de qualquer conclusão?

<Nota titulo="O que o MEEM 24 significa aqui">

Com quatro anos de estudo, 24 pontos está **dentro** da faixa esperada. O que sustenta a
suspeita não é o escore — é a mudança relatada em relação a como ele era.

</Nota>

<!--
Conduzir por perguntas, sem entregar. A resposta da terceira pergunta é o slide seguinte:
delirium, depressão e causas reversíveis (B12, tireoide, medicação) vêm antes.
-->

---
layout: comparacao
title: O que descartar primeiro
colunas:
  - { titulo: Delirium, sub: horas a dias, cor: terra }
  - { titulo: TNC maior, sub: meses a anos, cor: azul }
  - { titulo: Depressão, sub: semanas a meses, cor: verde }
linhas:
  - { criterio: Curso, valores: [flutua no mesmo dia, estável no dia e progressivo, pior pela manhã] }
  - { criterio: Atenção, valores: [prejudicada — é a marca, preservada no início, oscila com o humor] }
  - { criterio: Queixa, valores: [não se queixa, minimiza ou não percebe, detalha e amplifica] }
  - { criterio: No teste, valores: [não sustenta a tarefa, tenta e erra, responde "não sei"] }
---

<!--
Lembrar que os três coexistem com frequência, e que delirium sobreposto a TNC é a regra na
internação — não a exceção. Descartar não é escolher um.
-->

---
layout: default
---

# O tamanho do problema

<Grade :cols="3">

<Dado numero="8,5%" rotulo="das pessoas com 60 anos ou mais, no Brasil, vivem com demência" nota="ELSI-Brasil" />

<Dado numero="75%" rotulo="dos casos, no mundo, seguem sem diagnóstico formal" nota="Alzheimer's Disease International, 2021" />

<Dado numero="55 mi" rotulo="de pessoas com demência no mundo, e o número dobra a cada 20 anos" nota="OMS, 2021" />

</Grade>

<Nota titulo="O que esses números pedem de quem avalia">

O gargalo não é o instrumento — é o encaminhamento. A maior parte dos casos passa por alguém
que não perguntou.

</Nota>

---
layout: default
---

# O que a testagem não responde

<Citacao autor="Ronald Petersen" fonte="Journal of Internal Medicine, 2004">

O comprometimento cognitivo leve é um estado, não um destino.

</Citacao>

Uma bateria diz **o quanto** e **em quê**. Ela não diz *por quê*, não diz *quando começou* e
não diz *o que vai acontecer*. Isso vem da história, do informante, do exame físico, da
imagem e — principalmente — do
<span v-mark="{ at: 1, type: 'circle', class: 'ds-marca-marinho' }">tempo</span>.

<Nota tipo="ok" titulo="O que a reavaliação acrescenta">

Duas medidas separadas por doze meses dizem mais do que qualquer bateria isolada: elas
mostram a trajetória, que é o dado que o diagnóstico realmente precisa.

</Nota>

---
layout: fecho
kicker: Para levar
title: Três coisas que ficam
pontos:
  - Rastreio positivo não é diagnóstico — e rastreio negativo não descarta.
  - Escolaridade muda o ponto de corte, não a régua.
  - Sem informante e sem funcionalidade, não há síndrome — há escore.
proximo: Na próxima aula, os perfis cognitivos das principais etiologias — e o que distingue um perfil amnéstico de um disexecutivo.
---
