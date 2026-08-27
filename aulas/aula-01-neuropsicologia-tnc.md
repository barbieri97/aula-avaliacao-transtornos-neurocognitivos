---
theme: none
title: "Transtornos Neurocognitivos: alterações na cognição e funcionalidade"
info: Conceito, critérios diagnósticos, etiologias, domínios cognitivos e o
  lugar da avaliação neuropsicológica
date: "2026-09-14"
colorSchema: light
download: true
layout: capa
kicker: Semana da Psicologia · Psicologia e Neurociências
---

<!--
TNC — transtorno neurocognitivo.
DSM-5 — Manual Diagnóstico e Estatístico de Transtornos Mentais, 5ª edição (APA).
O capítulo de referência é o de Transtornos Neurocognitivos da edição brasileira (Artmed).
-->

---
layout: roteiro
kicker: Roteiro
title: O caminho de hoje
itens:
  - { tema: Conceito e classificação, desc: o que faz de um transtorno um TNC }
  - { tema: Critérios diagnósticos, desc: "delirium, TNC maior, TNC leve" }
  - { tema: Etiologias, desc: "a mesma síndrome, causas diferentes" }
  - { tema: Domínios cognitivos, desc: "o que se mede, e com o quê" }
  - { tema: Avaliação neuropsicológica, desc: cognição e funcionalidade }
---

<!--
Os cinco blocos reaparecem adiante como slides de seção, numerados de 01 a 05.
-->

---
layout: secao
numero: "01"
kicker: Bloco 1
title: Conceito e classificação
note: Déficits cognitivos existem em quase todo transtorno mental. Três características separam os que entram nesta categoria.
---

---
layout: default
---

# O que define um transtorno neurocognitivo

<Termo palavra="Transtorno neurocognitivo (TNC)" origem="DSM-5">

Déficit clínico **primário** na função cognitiva, **adquirido** — um declínio a partir de um
nível de funcionamento antes alcançado.

</Termo>

<Nota titulo="Duas palavras fazem o trabalho">

**Primário** exclui esquizofrenia e transtorno bipolar. **Adquirido** exclui deficiência
intelectual e transtorno específico da aprendizagem.

</Nota>

<Fonte>APA, <em>DSM-5</em> · capítulo Transtornos Neurocognitivos.</Fonte>

<!--
Na esquizofrenia e no bipolar há déficit cognitivo, mas a característica central é outra.
Na deficiência intelectual e no transtorno de aprendizagem a função nunca esteve preservada —
são transtornos do neurodesenvolvimento, capítulo próprio do DSM-5.

Texto do manual, para quem quiser a formulação inteira: "grupo de transtornos em que o
déficit clínico primário está na função cognitiva e em que a cognição prejudicada não estava
presente ao nascimento ou muito no início da vida — representando, portanto, um declínio a
partir de um nível de funcionamento alcançado anteriormente".
-->

---
layout: esquema
kicker: Bloco 1
title: Três marcas separam o TNC
legenda: "A terceira marca é a mais incomum no manual: em nenhuma outra categoria do DSM-5 a investigação da patologia subjacente faz parte da estrutura do diagnóstico."
---

<img src="/tnc-tres-marcas.svg" alt="As três marcas do TNC: déficit primário na cognição, caráter adquirido e etiologia determinável" class="w-full max-h-full object-contain">

<!--
Patologia subjacente: a alteração de tecido ou de circuito que produz o quadro — placas e
emaranhados na doença de Alzheimer, infartos na doença vascular, corpos de Lewy, príons.
-->

---
layout: comparacao
title: A mesma queixa, três lugares diferentes do manual
colunas:
  - { titulo: TNC, sub: adquirido, cor: azul }
  - { titulo: Neuro&shy;desenvolvimento, sub: de origem, cor: verde }
  - { titulo: Outro transtorno mental, sub: secundário, cor: terra }
linhas:
  - { criterio: Déficit central, valores: ["cognitivo", "cognitivo", "afetivo, psicótico ou ansioso"] }
  - { criterio: Curso de vida, valores: ["existiu e se perdeu", "nunca se instalou", "oscila com o quadro"] }
  - { criterio: Etiologia, valores: ["frequentemente determinável", "multifatorial", "não determinada"] }
  - { criterio: Exemplo, valores: ["perde o cálculo aos 70", "deficiência intelectual", "depressão com queixa de memória"] }
---

<!--
"Queixa de memória" é comum às três colunas — daí a do meio e a da direita serem os dois
diagnósticos diferenciais que mais aparecem na prática.
-->

---
layout: secao
numero: "02"
kicker: Bloco 2
title: Critérios diagnósticos
note: Delirium, TNC maior e TNC leve.
---

---
layout: default
---

# Delirium

<Criterios :itens="[
  { texto: 'Perturbação da <b>atenção</b> e da <b>consciência</b>.' },
  { texto: 'Instala-se em <b>horas a dias</b> e <b>oscila dentro do mesmo dia</b>.' },
  { texto: 'Há alteração cognitiva adicional: memória, orientação, linguagem.' },
  { texto: 'Não se explica por outro TNC preexistente, e não ocorre no coma.' },
  { texto: 'Tem causa fisiológica: doença, substância ou toxina.' },
]" />

<Fonte>Critérios A a E do delirium · APA, <em>DSM-5</em>.</Fonte>

<!--
Critério A por extenso: perturbação da atenção — dirigir, focalizar, manter e mudar o foco —
E da consciência (menor orientação para o ambiente).
Critério C: a perturbação adicional pode ser de memória, orientação, linguagem, capacidade
visuoespacial ou percepção.
Critério E: condição médica, intoxicação, abstinência, toxina ou múltiplas etiologias.
Basal: o estado habitual da pessoa antes do episódio.
Abstinência: quadro produzido pela retirada de uma substância de uso continuado.
-->

---
layout: esquema
kicker: Bloco 2
title: O que o tempo mostra
legenda: O delirium é o único quadro deste capítulo em que a <b>atenção</b> é a marca obrigatória — e o único cuja gravidade muda entre a visita da manhã e a da noite.
---

<img src="/curso-delirium-tnc.svg" alt="À esquerda o delirium oscilando ao longo de um dia; à direita o TNC declinando ao longo de anos" class="w-full max-h-full object-contain">

<!--
Delirium sobreposto a TNC é frequente na internação: os dois diagnósticos coexistem, e o
critério C do TNC exige apenas que os déficits não ocorram EXCLUSIVAMENTE no delirium.
-->

---
layout: default
---

# TNC maior

<Criterios :itens="[
  { texto: 'Declínio <b>importante</b> em um ou mais domínios: <b>queixa e prejuízo no teste</b>.' },
  { texto: 'Os déficits <b>interferem na independência</b> nas atividades instrumentais.' },
  { texto: 'Não ocorrem exclusivamente no contexto de um <b>delirium</b>.' },
  { texto: 'Não se explicam melhor por <b>outro transtorno mental</b>.' },
]" />

<Nota titulo="É o que se chama de demência">

*TNC maior* é mais amplo que o termo antigo: abrange também quem declinou em **um só domínio**.

</Nota>

<!--
O critério A pede as duas evidências: preocupação do próprio, de informante ou do clínico E
prejuízo documentado, de preferência por teste padronizado.
O critério D exclui, entre outros, depressão maior e esquizofrenia.
Declínio em um só domínio: o que o DSM-IV chamava de transtorno amnéstico — categoria para o
prejuízo isolado de memória. No DSM-5 passou a ser codificado como TNC maior devido a outra
condição médica, e nesse caso não se usa a palavra demência.
DSM-IV: a edição anterior do manual, de 1994.
Atividades instrumentais: as tarefas complexas do dia a dia, listadas no bloco 5.
-->

---
layout: comparacao
title: Maior e leve — o critério que muda é o B
colunas:
  - { titulo: TNC leve, sub: "o CCL", cor: ouro }
  - { titulo: TNC maior, sub: "a demência", cor: terra }
linhas:
  - { criterio: "A · declínio", valores: ["<b>pequeno</b> — prejuízo modesto no teste", "<b>importante</b> — prejuízo substancial"] }
  - { criterio: "B · independência", valores: ["<b>preservada</b>, com mais esforço ou estratégia", "<b>comprometida</b> — precisa de assistência"] }
  - { criterio: Exemplo, valores: ["passa a anotar o que antes lembrava", "erra a dose do próprio remédio"] }
---

<Nota tipo="alerta" titulo="A linha é clínica, não estatística">

Os critérios C e D são idênticos nos dois níveis. O que separa um do outro é a
**funcionalidade** — e ela não sai da tabela normativa.

</Nota>

<!--
C (não ocorre exclusivamente durante um delirium) e D (não é mais bem explicado por outro
transtorno mental) valem, com a mesma redação, para o TNC leve e para o maior.
A funcionalidade sai da história e do informante, não do escore.
CCL — comprometimento cognitivo leve, nome consagrado na literatura para o TNC leve.
AIVD — atividades instrumentais da vida diária: dinheiro, medicação, transporte, telefone,
compras, preparo de refeição.
-->

---
layout: esquema
kicker: Bloco 2
title: Uma linha, não três caixas
legenda: O corte entre uma faixa e a seguinte é uma convenção clínica — existe porque a conduta muda, não porque a natureza mude ali.
---

<Continuum :marcos="[
  { rotulo: 'Cognição típica', nota: 'sem queixa, sem alteração' },
  { rotulo: 'Comprometimento cognitivo subjetivo', nota: 'queixa <b>com</b> testes normais' },
  { rotulo: 'TNC leve', nota: 'declínio pequeno · independência preservada', destaque: true },
  { rotulo: 'TNC maior', nota: 'declínio importante · independência perdida' },
]" />

<Legenda :itens="[
  { cor: 'verde', texto: 'dentro do esperado para idade e escolaridade' },
  { cor: 'ouro', texto: 'declínio modesto, com esforço compensatório' },
  { cor: 'terra', texto: 'declínio substancial, com perda funcional' },
]" />

<!--
O comprometimento cognitivo subjetivo não é categoria do DSM-5; entra aqui porque é o que
costuma chegar primeiro ao consultório. O slide seguinte o define.
-->

---
layout: default
---

# Comprometimento cognitivo subjetivo

<Termo palavra="Comprometimento cognitivo subjetivo (CCS)" origem="Jessen et al., 2014">

Declínio **percebido pela própria pessoa**, persistente, **com desempenho normal** nos testes.
Não é categoria do DSM-5.

</Termo>

<Nota titulo="Queixa não é diagnóstico">

Pode ser a **primeira manifestação sintomática** da demência, anterior ao CCL. Ainda
assim a maior parte não evolui — o que o quadro pede é **acompanhamento**.

</Nota>

<Fonte>Jessen F. et al. A conceptual framework for research on subjective cognitive decline in preclinical Alzheimer disease. <em>Alzheimer&#39;s &amp; Dementia</em>, 2014.</Fonte>

<!--
A Subjective Cognitive Decline Initiative descreve o CCS como possível primeira manifestação
sintomática da doença de Alzheimer, anterior ao comprometimento cognitivo leve.
SCD — subjective cognitive decline, a sigla em inglês do CCS.
Pré-clínica: fase em que a patologia já existe mas ainda não produz alteração mensurável.
-->

---
layout: secao
numero: "03"
kicker: Bloco 3
title: Etiologias
note: O declínio vem primeiro. A etiologia é acrescentada depois.
---

---
layout: esquema
kicker: Bloco 3
title: Primeiro a síndrome, depois a causa
legenda: "O diagnóstico completo tem três partes — <b>nível</b> (leve ou maior), <b>etiologia</b> e <b>grau de certeza</b>. Por exemplo: \"TNC maior devido a provável doença de Alzheimer\"."
---

<img src="/sindrome-e-etiologia.svg" alt="A síndrome de TNC no centro, as etiologias em ramos e o par provável ou possível" class="w-full max-h-full object-contain">

<!--
Provável e possível: no DSM-5 o grau depende de evidência genética, de neuroimagem ou do
perfil clínico característico. Sem nenhuma delas, o subtipo fica como "possível".
TCE — traumatismo cranioencefálico.
-->

---
layout: default
---

# Principais Etiologias

<Grade :cols="3">

<Cartao rotulo="etiologia" titulo="Doença de Alzheimer" cor="azul">

Início insidioso, progressão gradual. Apresentação **amnéstica**.

</Cartao>

<Cartao rotulo="etiologia" titulo="Doença vascular" cor="azul">

Ligada a evento cerebrovascular. Declínio **atencional e executivo**.

</Cartao>

<Cartao rotulo="etiologia" titulo="Frontotemporal" cor="azul">

Variante **comportamental** ou **linguística**. Memória poupada.

</Cartao>

<Cartao rotulo="etiologia" titulo="Corpos de Lewy" cor="azul">

Cognição **oscilante**, alucinações visuais, parkinsonismo. Perfil **visuoperceptivo**.

</Cartao>

<Cartao rotulo="etiologia" titulo="Doença do príon" cor="azul">

**Rara** e **rápida** — meses. Mioclonia ou ataxia.

</Cartao>

<Cartao rotulo="e ainda" titulo="Outras" cor="cinza">

Parkinson, TCE, HIV, Huntington, substância, múltiplas etiologias.

</Cartao>

</Grade>

<Fonte>Subtipos etiológicos do <em>DSM-5</em>.</Fonte>

<!--
Alzheimer: memória e aprendizagem primeiro.
Vascular: ligada no tempo a um evento cerebrovascular, ou declínio em atenção complexa e
função executiva frontal.
Frontotemporal comportamental: desinibição, apatia, cognição social e executivas.
Linguística: afasia.
Corpos de Lewy: perfil visuoperceptivo e atencional, memória menos afetada — Mori et al.,
2000, e Calderón et al., 2001.
Príon: 1 a 2 casos por milhão ao ano.
Insidioso: de início lento e sem marco identificável.
Mioclonia: contração muscular breve e involuntária. Ataxia: incoordenação do movimento.
Afasia: perda adquirida da linguagem. Parkinsonismo: rigidez, bradicinesia e tremor.
-->

---
layout: figura
imagem: /alois-alzheimer.jpg
legenda: Alois Alzheimer (1864–1915). Em 1906 descreveu o caso de Auguste Deter, 51 anos. Retrato em <b>domínio público</b>, Wikimedia Commons.
lado: esquerda
ajuste: contain
---

# Uma causa nomeada não muda a síndrome

O diagnóstico de base continua sendo **TNC leve** ou **TNC maior**.

<Nota titulo="Por que o grau importa">

**Provável** exige evidência forte: mutação, neuroimagem ou o perfil clínico completo.
**Possível** é o que resta quando a clínica é compatível mas a confirmação não existe.

</Nota>

<!--
No TNC leve a confirmação costuma faltar: o DSM-5 observa que, nesse nível, com frequência o
mais apropriado é o subtipo "não especificado".
Alzheimer descreveu, na necropsia de Auguste Deter, a alteração do tecido cerebral que hoje
leva seu nome.
Necropsia: exame do corpo após a morte. Até hoje a confirmação definitiva de várias dessas
etiologias — a doença do príon inclusive — só é possível por biópsia ou necropsia.
-->

---
layout: figura
imagem: /hist-alzheimer.jpg
legenda: "Hipocampo, hematoxilina-eosina. No painel grande, a <b>placa neurítica</b> entre as setas; abaixo, à esquerda, o <b>emaranhado neurofibrilar</b> em chama, dentro do neurônio. Mikael Häggström e brainmaps.org, <b>CC BY 3.0</b>, Wikimedia Commons."
lado: direita
ajuste: contain
---

# Alzheimer: duas lesões, dois compartimentos

- **Fora** do neurônio — placas de **beta-amiloide**
- **Dentro** do neurônio — emaranhados de proteína **tau** hiperfosforilada
- Perda neuronal e atrofia cortical, a começar pelo hipocampo

<Nota titulo="A ordem das duas">

O amiloide se deposita antes e se espalha por fases; os emaranhados vêm depois, em estágios. É a distribuição dos **emaranhados** que acompanha o declínio cognitivo (Trejo-Lopez et al., 2021).

</Nota>

<!--
Beta-amiloide (Aβ): peptídeo derivado da clivagem da proteína precursora do amiloide (APP).
Tau: proteína que estabiliza os microtúbulos do neurônio; hiperfosforilada, solta-se deles e
se agrega em filamentos.
Hiperfosforilada: com excesso de grupos fosfato ligados à molécula.
Placa neurítica: depósito extracelular de amiloide cercado de prolongamentos neuronais doentes.
Fases de Thal (amiloide) e estágios de Braak (emaranhados): as duas escalas de distribuição
usadas na necropsia.
-->

---
layout: figura
imagem: /pet-amiloide-alzheimer.jpg
legenda: "PET com composto B de Pittsburgh. À esquerda, doença de Alzheimer; à
  direita, controle cognitivamente saudável. Vermelho e amarelo marcam alta
  ligação ao <b>beta-amiloide</b>. Klunk e Mathis, University of Pittsburgh,
  <b>CC BY-SA 3.0</b>, Wikimedia Commons."
lado: esquerda
ajuste: contain
---

# O que se vê antes da necropsia

- **PET de amiloide** — o depósito aparece cedo na cascata
- No líquido cerebrospinal, **beta-amiloide 42 baixa** e **tau alta**
- **Ressonância** — atrofia do hipocampo e do temporoparietal
- **PET com FDG** — hipometabolismo temporoparietal

<!--
PET: tomografia por emissão de pósitrons. FDG: fluordesoxiglicose, o marcador que mede
consumo de glicose e, por ele, a atividade do tecido.
Composto B de Pittsburgh (PiB): o primeiro traçador que se liga ao amiloide no cérebro vivo.
Líquido cerebrospinal (LCS): o líquido que banha o encéfalo e a medula, colhido por punção lombar.
Beta-amiloide 42: a fração de 42 aminoácidos, a que se agrega com mais facilidade. Cai no LCS
porque fica retida no cérebro.
Apolipoproteína E4 (APOE4) não é marcador diagnóstico: é fator de risco, nem necessário nem
suficiente.
-->

---
layout: default
---

# Alzheimer: onde, e o que cai

<Grade :cols="2">

<Cartao rotulo="regiões" titulo="Onde a lesão se instala" cor="azul">

- **Córtex entorrinal** e **hipocampo**, primeiro
- **Associação temporoparietal**, em seguida
- **Neocórtex** difuso, na fase maior

</Cartao>

<Cartao rotulo="cognição" titulo="O que cai, nesta ordem" cor="ouro">

- **Aprendizagem e memória** — a apresentação amnéstica
- **Função executiva**, já na fase leve
- **Visuoconstrutiva** e **linguagem**, na fase maior
- **Cognição social** poupada até tarde

</Cartao>

</Grade>

<Fonte>APA, <em>DSM-5</em> — TNC maior ou leve devido à doença de Alzheimer.</Fonte>

<!--
Córtex entorrinal: a porta de entrada do hipocampo, no lobo temporal medial.
Amnéstica: a apresentação em que a perda de memória é o achado principal. Há apresentações
não amnésticas, mais raras — a visuoespacial e a afásica logopênica.
Visuoconstrutiva: a capacidade de copiar ou montar uma figura.
Cognição social: reconhecer emoção no outro, ajustar o comportamento ao contexto.
-->

---
layout: figura
imagem: /rm-frontotemporal.png
legenda: "Ressonância em T2, T1 e FLAIR na doença de Pick. Os sulcos frontais estão alargados e os cornos frontais dilatados: a atrofia é anterior, e poupa o território posterior. Mikhail Kalinin, <b>CC BY-SA 3.0</b>, Wikimedia Commons."
lado: direita
ajuste: contain
---

# Frontotemporal: uma síndrome, três proteínas

- A patologia se chama **degeneração lobar frontotemporal** (DLFT)
- Três grupos moleculares: **tau**, **TDP-43** e **FET** (Neumann e Mackenzie, 2019)
- Mutações conhecidas: **MAPT**, **GRN**, **C9ORF72**

<Nota titulo="Herança e idade">

Cerca de **40%** têm história familiar de TNC precoce e **10%**, padrão autossômico dominante. É causa comum de TNC **antes dos 65 anos**.

</Nota>

<!--
DLFT: degeneração lobar frontotemporal, o achado de necropsia. TNC frontotemporal é a
síndrome clínica.
TDP-43: proteína de resposta transativa de ligação ao DNA de 43 kDa. FET: a família que reúne
FUS, EWS e TAF15.
MAPT: gene da proteína tau associada aos microtúbulos. GRN: gene da granulina.
C9ORF72: expansão repetida no cromossomo 9, ligada também à esclerose lateral amiotrófica.
Autossômico dominante: basta uma cópia alterada do gene para a doença aparecer.
FLAIR: sequência de ressonância que apaga o sinal do líquido e realça a lesão.
-->

---
layout: default
---

# Frontotemporal: onde, e o que cai

<Grade :cols="2">

<Cartao rotulo="regiões" titulo="Onde a atrofia aparece" cor="azul">

- **Frontal medial** e **temporal anterior** — variante comportamental
- **Temporal anterior esquerdo** — variante semântica
- **Insular-frontal posterior esquerdo** — variante não fluente

</Cartao>

<Cartao rotulo="cognição" titulo="O que cai" cor="ouro">

- **Cognição social** — desinibição, perda de empatia, apatia
- **Função executiva** — planejar, inibir, alternar
- **Linguagem**, nas variantes linguísticas
- **Memória** e **perceptomotor** relativamente poupados

</Cartao>

</Grade>

<Fonte>APA, <em>DSM-5</em> — TNC frontotemporal maior ou leve.</Fonte>

<!--
Variante comportamental: mudança de personalidade e conduta, com relativa preservação
cognitiva no início.
Variante semântica: perda do significado das palavras e dos objetos, com fala fluente.
Variante não fluente: fala esforçada e agramatical, com compreensão de palavra preservada.
Variante logopênica: pausas para encontrar a palavra e falha na repetição; costuma ser, na
verdade, doença de Alzheimer.
Insular: relativo à ínsula, o córtex escondido no fundo da fissura de Sylvius.
Perceptomotor: o domínio que reúne percepção visual, práxis e coordenação visuomotora.
-->

---
layout: figura
imagem: /rm-vascular-leucoaraiose.jpg
legenda: "Ressonância em FLAIR, corte coronal. As setas marcam a <b>leucoaraiose</b> — o hipersinal confluente da substância branca periventricular — em paciente com atrofia associada. Jmarchn, <b>CC BY-SA 3.0</b>, Wikimedia Commons."
lado: direita
ajuste: contain
---

# Vascular: a lesão é tecido perdido

- **Grande vaso** — o território arterial inteiro
- **Infarto estratégico** — tálamo, giro angular, prosencéfalo basal
- **Pequenos vasos** — lacunas e substância branca confluente

<Nota titulo="A certeza vem da imagem">

Sem neuroimagem o infarto silencioso passa despercebido. O DSM-5 só chama de **provável** com lesão documentada ou evento cerebrovascular datado.

</Nota>

<!--
Leucoaraiose: rarefação da substância branca, vista como hipersinal difuso na ressonância.
Também chamada de doença de pequenos vasos ou alteração isquêmica subcortical.
Lacuna: infarto pequeno e profundo, de um ramo arterial terminal.
Infarto estratégico: lesão única que, pela posição, basta para o quadro cognitivo.
Prosencéfalo basal: região da base do cérebro, origem da inervação colinérgica do córtex.
CADASIL: arteriopatia cerebral autossômica dominante com infartos subcorticais e
leucoencefalopatia — a forma hereditária.
Angiopatia amiloide cerebral: depósito de amiloide na parede dos vasos.
-->

---
layout: default
---

# Vascular: onde, e o que cai

<Grade :cols="2">

<Cartao rotulo="regiões" titulo="Onde a lesão se instala" cor="azul">

- **Substância branca** frontal e periventricular
- **Núcleos da base** e **tálamo**
- O que se rompe é o **circuito córtico-subcortical**

</Cartao>

<Cartao rotulo="cognição" titulo="O que cai" cor="ouro">

- **Velocidade de processamento** — o critério B do DSM-5
- **Atenção complexa**
- **Função executiva frontal**
- Memória responde melhor à **pista** que no Alzheimer

</Cartao>

</Grade>

<Fonte>APA, <em>DSM-5</em> — TNC vascular maior ou leve; subtipos em Sachdev et al., 2014.</Fonte>

<!--
Circuito córtico-subcortical: as alças que ligam o córtex pré-frontal aos núcleos da base e ao
tálamo, e voltam ao córtex. A lesão da substância branca as interrompe.
Velocidade de processamento: quanto tempo se leva para executar uma tarefa cognitiva simples;
mede-se cronometrando.
Depressão vascular: sintomas depressivos tardios com lentificação e disfunção executiva, em
idosos com doença isquêmica de pequenos vasos.
-->

---
layout: figura
imagem: /hist-lewy-sinucleina.jpg
legenda: "Neocórtex, imuno-histoquímica para <b>alfa-sinucleína</b>. Em
  castanho, os <b>corpos de Lewy</b> — os grumos arredondados — e as <b>neuritas
  de Lewy</b>, os filamentos finos. Movalley, <b>CC0</b>, Wikimedia Commons."
lado: esquerda
ajuste: contain
---

# Corpos de Lewy: uma sinucleinopatia

- Agregados de **alfa-sinucleína** mal enovelada dentro do neurônio
- No TNC com corpos de Lewy eles são sobretudo **corticais**
- Na doença de Parkinson, sobretudo nos **núcleos da base**

<!--
Alfa-sinucleína: proteína pré-sináptica que, mal enovelada, se agrega em corpos e neuritas.
Sinucleinopatia: a família de doenças definidas por esses agregados.
Imuno-histoquímica: técnica que marca uma proteína específica com anticorpo, e a revela em
castanho no tecido.
Corpo de Lewy: inclusão arredondada no corpo do neurônio. Neurita de Lewy: a mesma proteína
agregada dentro do prolongamento.
Mal enovelada: com a forma tridimensional errada, o que a torna insolúvel e propensa a agregar.
-->

---
layout: default
---

# Corpos de Lewy: onde, e o que cai

<Grade :cols="2">

<Cartao rotulo="regiões" titulo="Onde a lesão se instala" cor="azul">

- **Córtex occipital** — hipometabolismo em PET e SPECT
- **Via nigroestriatal** — captação reduzida do transportador de dopamina
- **Temporal medial** relativamente **preservado**

</Cartao>

<Cartao rotulo="cognição" titulo="O que cai" cor="ouro">

- **Atenção complexa** — e ela **oscila** ao longo do dia
- **Função executiva**
- **Visuoperceptivo** e **visuoconstrutivo**
- **Memória** menos afetada no começo

</Cartao>

</Grade>

<Fonte>APA, <em>DSM-5</em>; marcadores em McKeith et al., 2017.</Fonte>

<!--
SPECT: tomografia computadorizada por emissão de fóton único.
Via nigroestriatal: o feixe dopaminérgico que liga a substância negra ao estriado.
Transportador de dopamina (DAT): a proteína que recolhe a dopamina da fenda sináptica; a
captação baixa indica perda dos terminais.
Cintilografia miocárdica com MIBG: exame que mostra denervação simpática do coração, marcador
sugestivo no consenso de 2017.
Sono REM: fase do sono com movimento rápido dos olhos. No transtorno comportamental do sono
REM a pessoa executa fisicamente o que sonha.
Sensibilidade neuroléptica: reação grave a antipsicóticos, em até metade dos casos.
-->

---
layout: figura
imagem: /hist-prion-espongiforme.jpg
legenda: "Córtex em hematoxilina-eosina na variante da doença de Creutzfeldt-Jakob. Os vacúolos claros dão ao tecido o aspecto de esponja, sem sinal de inflamação. Zaki e Shieh, CDC / Public Health Image Library #10131, <b>domínio público</b>."
lado: direita
ajuste: contain
---

# Príon: uma proteína que muda de forma

- A **PrP** normal é rica em **alfa-hélice**; a alterada, em **folha beta**
- A forma alterada **molda** as moléculas seguintes — ela se autopropaga
- O resultado é a **encefalopatia espongiforme** (Colby e Prusiner, 2011)

<Nota tipo="alerta" titulo="Rara e rápida">

Cerca de **1 a 2 casos por milhão** ao ano. Progride para TNC maior em **semanas a meses**, não em anos.

</Nota>

<!--
Príon: partícula infecciosa feita só de proteína, sem ácido nucleico.
PrP: proteína priônica. PrP-C é a isoforma celular normal; PrP-Sc, a isoforma patogênica,
insolúvel e resistente às proteases.
Alfa-hélice e folha beta: as duas formas básicas de dobramento de uma cadeia de proteína.
DCJ: doença de Creutzfeldt-Jakob. A esporádica é a mais comum; a variante está ligada à
encefalopatia espongiforme bovina.
Encefalopatia espongiforme: perda neuronal com vacúolos no tecido, sem inflamação.
Kuru, síndrome de Gerstmann-Sträussler-Scheinker e insônia fatal completam o grupo.
-->

---
layout: figura
imagem: /rm-prion-flair.jpg
legenda: "Ressonância na doença de Creutzfeldt-Jakob. <b>A</b> e <b>B</b>: hipersinal nos núcleos da base em FLAIR e em DWI. <b>C</b>: a fita cortical. <b>D</b>: o tálamo. <i>Practical Neurology</i>, <b>CC BY 4.0</b>, Wikimedia Commons."
lado: esquerda
ajuste: contain
---

# O exame que sustenta a suspeita

- **Ressonância com DWI** — hoje o teste mais sensível
- **Eletrencefalograma** — descargas trifásicas periódicas, de 0,5 a 2 Hz
- No líquido cerebrospinal, proteína **14-3-3** e **tau**

<Nota titulo="A confirmação definitiva">

Só por **biópsia ou necropsia**. O DSM-5 pede ao menos um marcador característico antes de dar o diagnóstico.

</Nota>

<!--
DWI: difusão ponderada, sequência de ressonância sensível ao movimento das moléculas de água.
Fita cortical: o hipersinal fino que acompanha o contorno do córtex.
Eletrencefalograma (EEG): registro da atividade elétrica do córtex. Hz: hertz, ciclos por segundo.
Onda trifásica: onda lenta com três deflexões, achado clássico mas nem sempre presente.
Proteína 14-3-3: marcador de destruição neuronal rápida; útil sobretudo na DCJ esporádica.
-->

---
layout: default
---

# Príon: onde, e o que cai

<Grade :cols="2">

<Cartao rotulo="regiões" titulo="Onde o sinal aparece" cor="azul">

- **Córtex** — a fita cortical em DWI e FLAIR
- **Estriado** — caudado e putame
- **Tálamo**, sobretudo na variante
- **Cerebelo**, nos sinais motores

</Cartao>

<Cartao rotulo="cognição" titulo="O que cai" cor="ouro">

- Declínio **global**, e não de um domínio só
- Junto vêm **mioclonia**, **ataxia** e reflexo de sobressalto
- Na variante, os sintomas **psiquiátricos** vêm antes

</Cartao>

</Grade>

<Fonte>APA, <em>DSM-5</em> — TNC maior ou leve devido à doença do príon.</Fonte>

<!--
Estriado: caudado e putame, dois dos núcleos da base.
Mioclonia: contração muscular breve e involuntária. Ataxia: incoordenação do movimento.
Reflexo de sobressalto: resposta motora exagerada a um estímulo súbito.
Pela velocidade, o transtorno costuma ser encontrado só no nível maior — quase não há
janela de TNC leve.
-->

---
layout: comparacao
title: Cinco etiologias, cinco assinaturas
colunas:
  - { titulo: Lesão, sub: o que se acumula ou se perde, cor: terra }
  - { titulo: Regiões, sub: onde ela se instala, cor: azul }
  - { titulo: O que cai primeiro, sub: o domínio de entrada, cor: ouro }
linhas:
  - {
      criterio: Alzheimer,
      valores:
        [
          "placas de <b>beta-amiloide</b> e emaranhados de <b>tau</b>",
          "entorrinal e hipocampo",
          "aprendizagem e memória"
        ]
    }
  - {
      criterio: Frontotemporal,
      valores:
        [
          "DLFT — <b>tau</b>, <b>TDP-43</b> ou <b>FET</b>",
          "frontal medial e temporal anterior",
          "cognição social e executiva"
        ]
    }
  - {
      criterio: Vascular,
      valores:
        [
          "infarto e lesão da substância branca",
          "circuito córtico-subcortical",
          "velocidade e executiva"
        ]
    }
  - {
      criterio: Corpos de Lewy,
      valores:
        [
          "agregados de <b>alfa-sinucleína</b>",
          "occipital e nigroestriatal",
          "atenção complexa, oscilante"
        ]
    }
  - {
      criterio: Príon,
      valores:
        [
          "<b>PrP</b> mal enovelada, tecido espongiforme",
          "córtex, estriado e tálamo",
          "tudo, em poucos meses"
        ]
    }
---

<Fonte>Síntese do capítulo de Transtornos Neurocognitivos do <em>DSM-5</em>.</Fonte>

<!--
A tabela lê-se da esquerda para a direita: a lesão explica a região, e a região explica o
domínio. Nenhuma linha é exclusiva — patologias mistas são a regra no idoso, e nesse caso o
DSM-5 pede o subtipo "devido a múltiplas etiologias".
-->

---
layout: secao
numero: "04"
kicker: Bloco 4
title: Domínios cognitivos
note: É aqui que o neuropsicólogo entra. A alteração nos domínios é o critério A — o que sustenta o diagnóstico.
---

---
layout: esquema
kicker: Bloco 4
title: Os seis domínios
legenda: O DSM-5 define os domínios em uma tabela de três colunas — o nome, os exemplos de sintomas e os exemplos de avaliação. Os dois próximos slides a condensam.
---

<img src="/seis-dominios.svg" alt="Os seis domínios neurocognitivos do DSM-5 dispostos ao redor de um centro" class="w-full max-h-full object-contain">

<!--
Tabela 1 do capítulo, "Domínios neurocognitivos". Os mesmos seis nomes aparecem, na mesma
ordem, dentro do critério A do TNC maior e do TNC leve.
-->

---
layout: comparacao
title: Domínios · 1 de 2
colunas:
  - { titulo: Sintomas ou observações, sub: o que se vê no dia a dia, cor: azul }
  - { titulo: Exemplos de avaliação, sub: o que o teste pede, cor: ouro }
linhas:
  - { criterio: Atenção complexa, valores: ["distrai-se com TV e conversa ao redor; não retém um telefone recém-dito", "atenção sustentada, seletiva e dividida; velocidade de processamento"] }
  - { criterio: Função executiva, valores: ["abandona projetos complexos; multitarefa fica difícil", "planejamento; memória de trabalho; inibição; flexibilidade mental"] }
  - { criterio: Aprendizagem e memória, valores: ["repete-se na mesma conversa; conta cada vez mais com lista e calendário", "<b>evocação livre</b>, <b>com pistas</b> e <b>reconhecimento</b>; memória semântica"] }
---

<Fonte>Tabela 1 — Domínios neurocognitivos · APA, <em>DSM-5</em>. Texto condensado.</Fonte>

<!--
Atenção complexa: todo pensamento leva mais tempo que o normal. Velocidade de processamento
se quantifica cronometrando a tarefa.
Função executiva: passa a depender de outros para planejar; retomar tarefa interrompida cansa.
Testes de planejamento (labirinto), tomada de decisão, resposta a feedback.
Memória de trabalho: manter uma informação por período curto E manipulá-la — série de números
de trás para a frente.
Memória semântica: memória de fatos. Autobiográfica: de eventos e pessoas da própria vida.
Aprendizagem implícita: aprendizagem inconsciente de procedimentos e habilidades.
-->

---
layout: comparacao
title: Domínios · 2 de 2
colunas:
  - { titulo: Sintomas ou observações, sub: o que se vê no dia a dia, cor: azul }
  - { titulo: Exemplos de avaliação, sub: o que o teste pede, cor: ouro }
linhas:
  - { criterio: Linguagem, valores: ["dificuldade para achar palavras; usa \"aquela coisa\"; adiante, ecolalia e mutismo", "nomeação confrontativa; fluência semântica e fonêmica; compreensão de comando"] }
  - { criterio: Perceptomotor, valores: ["perde-se em ambiente conhecido; dificuldade para dirigir e usar ferramenta", "visuoconstrutiva (copiar, montar); práxis; gnosia de rostos e cores"] }
  - { criterio: Cognição social, valores: ["comportamento fora da variação aceitável; menos empatia; decide sem pesar risco", "reconhecimento de emoções em rostos; teoria da mente"] }
---

<Fonte>Tabela 1 — Domínios neurocognitivos · APA, <em>DSM-5</em>. Texto condensado.</Fonte>

<!--
Linguagem: prefere pronome genérico, erra artigo e preposição. A fluência é medida em um
minuto; a linguagem receptiva, por compreensão e execução de comando verbal.
Perceptomotor: confunde-se ao anoitecer, estaciona com menos precisão. Também percepção visual
sem mediação verbal e tarefas perceptomotoras (encaixar pinos).
Cognição social: insensibilidade a padrões de pudor; decide sem considerar a segurança; no
leve, mudança sutil de atitude. Teoria da mente se avalia com cartões que contam uma história
e perguntas sobre o estado mental dos personagens.
Nomeação confrontativa: mostrar uma figura e pedir o nome.
Fluência semântica: itens de uma categoria (animais); fonêmica: palavras começadas por uma letra.
Práxis: integridade dos movimentos aprendidos. Gnosia: integridade do reconhecimento.
Ecolalia: repetição da fala do interlocutor. Mutismo: ausência de fala.
-->

---
layout: default
---

# O mesmo domínio, dois níveis

<Grade :cols="2">

<Cartao rotulo="aprendizagem e memória" titulo="No TNC maior" cor="terra">

Repete-se **na mesma conversa**. Não se atém a uma lista curta de compras. Precisa de
lembretes frequentes.

</Cartao>

<Cartao rotulo="aprendizagem e memória" titulo="No TNC leve" cor="ouro">

Conta **cada vez mais com listas e calendário**. Precisa reler para acompanhar os personagens
de um livro.

</Cartao>

</Grade>

<Nota titulo="O que essa comparação mostra">

Não são sintomas diferentes: é o **mesmo sintoma em outra intensidade**. Por isso o critério
que separa os níveis não está no domínio, e sim na funcionalidade.

</Nota>

<Fonte>Tabela 1, linha "Aprendizagem e memória" · APA, <em>DSM-5</em>.</Fonte>

<!--
No maior: precisa de lembretes frequentes para orientar uma tarefa em andamento.
No leve: dificuldade de recordar eventos recentes; lembretes ocasionais; não sabe dizer se as
contas já foram pagas.
-->

---
layout: esquema
kicker: Bloco 4
title: O resultado é um perfil, não um número
legenda: "Seis medidas do mesmo paciente. É a <b>forma</b> do perfil — e não a média dela — que orienta a hipótese etiológica: aqui, memória rebaixada com executivas limítrofes."
---

<Perfil :dominios="[
  { nome: 'Atenção complexa', z: -0.5 },
  { nome: 'Função executiva', z: -1.6 },
  { nome: 'Aprendizagem e memória', z: -2.7 },
  { nome: 'Linguagem', z: -0.9 },
  { nome: 'Perceptomotor', z: -1.1 },
  { nome: 'Cognição social', z: -0.2 },
]" />

<Legenda :itens="[
  { cor: 'ok', texto: 'dentro do esperado (até −1 DP)' },
  { cor: 'warn', texto: 'limítrofe (−1 a −2 DP)' },
  { cor: 'danger', texto: 'rebaixado (abaixo de −2 DP)' },
]" />

<!--
z (escore z) e DP (desvio-padrão): quantos desvios o desempenho está acima ou abaixo da
média do grupo normativo de mesma idade e escolaridade. z = −2 corresponde ao percentil 2.
Perfil ilustrativo, não um caso real.
-->

---
layout: secao
numero: "05"
kicker: Bloco 5
title: Avaliação neuropsicológica — função e cognição
---

---
layout: esquema
kicker: Bloco 5
title: Duas perguntas, não uma
legenda: "As duas metades vêm de fontes diferentes: a primeira, da testagem padronizada; a segunda, da entrevista com quem convive com a pessoa."
---

<img src="/cognicao-e-funcionalidade.svg" alt="À esquerda a medida da cognição por domínio; à direita a checagem das atividades instrumentais" class="w-full max-h-full object-contain">

<!--
O critério A do TNC exige as duas evidências: preocupação (do próprio, de informante ou do
clínico) E prejuízo documentado. Uma sozinha não fecha o critério.
-->

---
layout: pergunta
kicker: Bloco 5 · para discutir
title: O escore caiu. <em>por qual caminho?</em>
pistas:
  - Prejuízo de memória ou de atenção?
  - A memória melhora com dica?
  - Atenção ou controle inibitório?
  - Esquecimento ou acesso lexical?
---

Um escore baixo é o **fim** de uma cadeia, não o começo. Separar as hipóteses que levam a ele
é o trabalho da avaliação neuropsicológica — **nenhum rastreio faz isso**.

<!--
A mesma pontuação em evocação livre pode vir de não ter prestado atenção, de não ter guardado,
de não conseguir buscar ou de não achar a palavra — e cada uma dessas hipóteses leva a uma
conduta diferente.
Acesso lexical: a recuperação da forma da palavra na memória de longo prazo — o "está na
ponta da língua". É função de linguagem, não de memória episódica.
Rastreio: instrumento breve de triagem, como o MEEM ou o MoCA, que produz um escore global.
-->

---
layout: default
---

# As quatro perguntas por trás do escore

<Criterios :itens="[
  { letra: '1', titulo: 'Memória ou atenção?', texto: 'o material chegou a entrar?' },
  { letra: '2', titulo: 'A memória melhora com dica?', texto: 'o item estava guardado, ou não estava?' },
  { letra: '3', titulo: 'Atenção ou controle inibitório?', texto: 'sustentar o foco, ou vencer o automático?' },
  { letra: '4', titulo: 'Esquecimento ou acesso lexical?', texto: 'memória episódica, ou linguagem?' },
]" />

<!--
AS RESPOSTAS — não estão no slide de propósito; são a fala.

1. Memória ou atenção? Se a atenção não sustentou a tarefa, o material nunca foi codificado, e
   o que parece esquecimento é falha de entrada. Compara-se a memória imediata com a recente,
   e as duas com a atenção sustentada e a velocidade de processamento.

2. Melhora com dica? Comparam-se evocação livre, evocação com pistas e reconhecimento — as três
   formas que o próprio DSM-5 lista. Se a pista recupera o item, ele estava guardado. Se não
   recupera, não estava.

3. Atenção ou inibição? São coisas diferentes na tabela: atenção seletiva é manter o foco
   apesar do distrator; substituição de hábitos e inibição é escolher a resposta difícil em vez
   da automática — nomear a cor da fonte, e não a palavra escrita.

4. Esquecimento ou acesso lexical? "Não lembro o nome" pode ser memória ou linguagem. A nomeação
   confrontativa e a fluência separam as duas: quem tem anomia falha em nomear a figura que está
   vendo — não há nada a esquecer ali.

Anomia: dificuldade específica para nomear, com compreensão preservada.
Codificação: a entrada da informação no sistema de memória. Armazenamento: a manutenção dela ao
longo do tempo. Evocação: a recuperação.
-->

---
layout: esquema
kicker: Bloco 5
title: Livre, com pista, reconhecimento
legenda: Grober e Buschke mostraram que a evocação com pista, depois de uma codificação controlada, separa o déficit genuíno de memória do prejuízo aparente produzido por atenção ou por busca ineficiente.
---

<img src="/memoria-com-dica.svg" alt="Dois padrões de recuperação: um paciente melhora com a pista, o outro não" class="w-full max-h-full object-contain">

<!--
Grober E. e Buschke H. Genuine memory deficits in dementia. Developmental Neuropsychology,
1987. O paradigma deu origem ao FCSRT (Free and Cued Selective Reminding Test).
-->

---
layout: default
---

# A outra metade: funcionalidade

<Termo palavra="Atividades instrumentais da vida diária (AIVD)" origem="DSM-5, critério B">

As tarefas complexas de manter a própria vida: **pagar contas, controlar a medicação**, usar
transporte, telefone, fazer compras, preparar refeição.

</Termo>

<Nota titulo="Três coisas que só a entrevista responde">

**Existe prejuízo funcional?** **Quando começou e como andou?** **O que mais está em jogo?**

</Nota>

<Fonte>APA, <em>DSM-5</em>, critério B · escala de informante validada para o Brasil: <b>P-FAQ</b> (Assis L.O. et al., 2014).</Fonte>

<!--
São as instrumentais — e não as básicas, como vestir-se e alimentar-se — que o critério B
examina.
Prejuízo funcional: em relação ao que a pessoa fazia antes.
Início e curso: súbito ou insidioso, em degraus ou contínuo.
O que mais está em jogo: medicação, álcool, déficit sensorial não corrigido, dor, insônia,
doença clínica descompensada.
Informante: pessoa que convive com o paciente e pode relatar mudanças — não precisa ser
familiar, mas precisa ter convivência regular e anterior ao quadro.
-->

---
layout: esquema
kicker: Bloco 5
title: A ordem do raciocínio
legenda: "A sequência não é obrigatória nem de mão única: um achado da história muda a hipótese e faz o caminho voltar atrás."
---

<Fluxo :por-linha="4" :etapas="[
  { titulo: 'Queixa', desc: 'do próprio ou do informante' },
  { titulo: 'Nível prévio', desc: 'escolaridade e ocupação' },
  { titulo: 'Início e curso', desc: 'quando começou, como andou' },
  { titulo: 'Comorbidades', desc: 'clínicas, psiquiátricas, medicações' },
  { titulo: 'Testagem', desc: 'os seis domínios, com norma adequada', cor: 'ouro' },
  { titulo: 'Funcionalidade', desc: 'AIVD, com informante' },
  { titulo: 'Diferencial', desc: 'e só então a etiologia' },
]" />

<!--
Nível prévio de desempenho: o critério A do DSM-5 pede comparação com ele, não com a média
da população. Escolaridade e ocupação são as estimativas de que se dispõe na prática.
Comorbidade: outra condição presente ao mesmo tempo.
A queixa pode vir também do clínico.
-->

---
layout: fecho
kicker: Para levar
title: Três coisas que ficam
pontos:
  - Déficit primário, adquirido, com etiologia buscada — e a síndrome vem antes da causa.
  - "O que separa leve de maior não é o escore: é a independência."
  - Um escore baixo tem muitas origens. Separá-las é o trabalho do neuropsicólogo.
---

---
layout: default
---

<img src="/oqueachamoquee.jpg" alt="As três marcas do TNC: déficit primário na cognição, caráter adquirido e etiologia determinável" class="w-full max-h-full object-contain">

---
layout: default
---

# Referências

<Criterios :itens="[
  { letra: '·', texto: '<b>American Psychiatric Association.</b> <i>DSM-5</i>. Porto Alegre: Artmed. Capítulo <b>Transtornos Neurocognitivos</b> — <b>base primária desta aula</b>.' },
  { letra: '·', texto: '<b>Jessen F. et al., 2014.</b> A conceptual framework for research on subjective cognitive decline in preclinical Alzheimer disease. <i>Alzheimer’s &amp; Dementia</i>, 10(6):844-52.' },
  { letra: '·', texto: '<b>Grober E. e Buschke H., 1987.</b> Genuine memory deficits in dementia. <i>Developmental Neuropsychology</i>, 3(1):13-36.' },
  { letra: '·', texto: '<b>Mori E. et al., 2000</b>, <i>Archives of Neurology</i>, 57(4):489-93; <b>Calderón J. et al., 2001</b>, <i>J Neurol Neurosurg Psychiatry</i>, 70(2):157-64.' },
  { letra: '·', texto: '<b>Assis L.O. et al., 2014.</b> Brazilian version of Pfeffer’s Functional Activities Questionnaire. <i>Frontiers in Aging Neuroscience</i>, 6:255.' },
]" />

<Fonte>Retrato de Alois Alzheimer: Wikimedia Commons, <b>domínio público</b>. Os esquemas são autorais.</Fonte>

---
layout: default
---

# Referências · etiologias

<Criterios :itens="[
  { letra: '·', texto: '<b>Trejo-Lopez J.A., Yachnis A.T. e Prokop S., 2021.</b> Neuropathology of Alzheimer&rsquo;s disease. <i>Neurotherapeutics</i>, 19(1):173-85. doi:10.1007/s13311-021-01146-y' },
  { letra: '·', texto: '<b>Neumann M. e Mackenzie I.R.A., 2019.</b> Neuropathology of non-tau frontotemporal lobar degeneration. <i>Neuropathology and Applied Neurobiology</i>, 45(1):19-40. doi:10.1111/nan.12526' },
  { letra: '·', texto: '<b>Sachdev P. et al., 2014.</b> Diagnostic criteria for vascular cognitive disorders: a VASCOG statement. <i>Alzheimer Disease &amp; Associated Disorders</i>, 28(3):206-18. doi:10.1097/WAD.0000000000000034' },
  { letra: '·', texto: '<b>McKeith I.G. et al., 2017.</b> Diagnosis and management of dementia with Lewy bodies: fourth consensus report of the DLB Consortium. <i>Neurology</i>, 89(1):88-100. doi:10.1212/WNL.0000000000004058' },
  { letra: '·', texto: '<b>Colby D.W. e Prusiner S.B., 2011.</b> Prions. <i>Cold Spring Harbor Perspectives in Biology</i>, 3(1):a006833. doi:10.1101/cshperspect.a006833' },
]" />

<Fonte>As imagens de exame vêm do Wikimedia Commons, creditadas slide a slide.</Fonte>

<!--
As cinco referências complementam o DSM-5 no que ele não detalha: o estadiamento das lesões
do Alzheimer, a classificação molecular da degeneração frontotemporal, os subtipos vasculares,
os biomarcadores dos corpos de Lewy e o mecanismo da conversão priônica.
doi: identificador digital de objeto — o endereço permanente de um artigo científico.
-->


