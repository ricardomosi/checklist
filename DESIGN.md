---
name: "Checklist 5S e Gestão Industrial de Frotas — JPatrício"
description: "Interface clara de operação e manutenção, com superfícies brancas, texto grafite e ações em cobre."
colors:
  canvas: "#f4f6f8"
  surface: "#fff"
  ink: "#243344"
  muted: "#526170"
  line: "#dce2e8"
  accent: "#a84613"
  accent-soft: "#fff2e8"
  accent-hover: "#87370d"
  slate-strong: "#0f172a"
  slate-soft: "#f1f5f9"
  field-line: "#cbd5e1"
  success: "#047857"
  danger: "#b91c1c"
typography:
  headline:
    fontFamily: "Inter, system-ui, -apple-system, sans-serif"
    fontSize: "1.5rem"
    fontWeight: 650
    lineHeight: 1.3
    letterSpacing: "-.025em"
  title:
    fontFamily: "Inter, system-ui, -apple-system, sans-serif"
    fontSize: ".9375rem"
    fontWeight: 700
    lineHeight: 1.5
  body:
    fontFamily: "Inter, system-ui, -apple-system, sans-serif"
    fontSize: ".8125rem"
    fontWeight: 400
    lineHeight: 1.5
  label:
    fontFamily: "Inter, system-ui, -apple-system, sans-serif"
    fontSize: ".75rem"
    fontWeight: 550
    lineHeight: 1.5
  operator-measurement:
    fontFamily: "JetBrains Mono, monospace"
rounded:
  control: "7px"
  card: "8px"
  summary: "10px"
  panel: "12px"
  modal: "24px"
  chip: "4px"
  pill: "9999px"
spacing:
  compact: "6px"
  small: "8px"
  medium: "12px"
  card: "14px"
  section: "16px"
  spacious: "24px"
  workspace: "28px"
components:
  button-primary:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.surface}"
    rounded: "{rounded.panel}"
    padding: "14px"
  button-primary-hover:
    backgroundColor: "{colors.accent-hover}"
    textColor: "{colors.surface}"
  search-field:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.slate-strong}"
    rounded: "{rounded.card}"
    padding: "8px 6px 8px 28px"
  manager-navigation:
    backgroundColor: "transparent"
    textColor: "{colors.muted}"
    rounded: "{rounded.control}"
    padding: "10px 12px"
  manager-navigation-selected:
    backgroundColor: "{colors.accent-soft}"
    textColor: "#963e10"
    rounded: "{rounded.control}"
    padding: "10px 12px"
  urgency-chip:
    backgroundColor: "rgb(239 68 68 / 0.2)"
    textColor: "{colors.danger}"
    rounded: "{rounded.chip}"
    padding: "0 6px"
  maintenance-card:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.slate-strong}"
    rounded: "{rounded.card}"
    padding: "{spacing.card}"
---

# Design System: JPatrício

## Overview

**Creative North Star: "Quadro de programação da oficina"**

A interface usa superfícies brancas, fundo cinza claro e texto grafite para apoiar trabalho recorrente em português brasileiro. A direção clara e profissional privilegia leitura, identificação de estados e controles previsíveis.

O modo de gestão tem densidade de interface operacional; o operador mantém etapas guiadas e respostas grandes para uso no chão de fábrica. Inter é uma escolha intencional para esse contexto Operate. Esta documentação descreve a combinação implementada de index.html, utilitários Tailwind e sobrescritas em gestao.css.

**Key Characteristics:**

- Superfícies claras e separação por bordas.
- Ações principais em cobre e estados acompanhados de texto.
- Gestão compacta, operador com alvos amplos.
- Navegação e conteúdo adaptados a telas estreitas.

## Colors

O cobre identifica ações; cinzas frios organizam a estrutura, e cores semânticas comunicam condições operacionais.

### Primary

O token accent é o cobre de envio e confirmação; accent-hover escurece a ação sob o ponteiro. accent-soft marca a navegação atual e o controle de ampliação ativo.

### Secondary

Success e danger representam conformidade e falha. O Kanban conserva bordas de etapa âmbar, laranja, azul e esmeralda dos utilitários existentes. A urgência usa vermelho translúcido com rótulo explícito. Essas cores são semânticas, não novos acentos de marca.

### Neutral

Canvas ocupa a área de trabalho; surface identifica conteúdo. Ink e muted formam a hierarquia de texto, line delimita superfícies e field-line contorna campos. Os utilitários legados preservam slate-strong em títulos e slate-soft em controles neutros. Não substituir essa cascata presumindo que todo texto herda ink.

**The Estado Legível Rule.** Identifique estados com texto e cor; preserve o indicador Online/Offline também no celular.

## Typography

Inter, com fallback de sistema, é a fonte de interface. O título da área usa headline; títulos de painéis usam title; conteúdo compacto usa body e rótulos de filtros usam label. Não existe papel display independente no painel.

A raiz mede 16px e passa a 18px quando o usuário aciona A+. Em até 600px, o título da área passa a 1.25rem e campos de gestão a 1rem. Números no conteúdo da gestão usam Inter com algarismos tabulares.

JetBrains Mono é a referência para medições do operador. A implementação ainda aplica a classe monoespaçada ao PIN e a campos em modais fora do contêiner de gestão; isso é um resíduo existente, não uma orientação para novas telas. Os pesos 550 e 650 estão declarados no CSS, enquanto o carregamento de fontes lista pesos discretos; o resultado depende da resolução de peso do navegador.

**The Tipografia Operacional Rule.** Use Inter em novas áreas de gestão e reserve a fonte monoespaçada para leituras técnicas do operador.

## Layout

A aplicação ocupa 100dvh; o cabeçalho não encolhe e o conteúdo tem rolagem interna. No desktop, a lateral de gestão mede 212px, com navegação vertical; o conteúdo ocupa o espaço restante e tem recuo lateral de 28px. O operador usa largura máxima de 28rem.

O Kanban apresenta duas colunas por padrão e quatro a partir de 1440px. Em até 1000px, a navegação passa a faixa horizontal rolável e o conteúdo usa recuo de 20px. Em até 600px, o Kanban tem uma coluna, o recuo cai a 14px, filtros se empilham, o cabeçalho permite quebra e a área do operador perde borda e raio externos.

O calendário conserva largura mínima de 700px e rolagem horizontal local. Tabelas compactas conservam largura mínima de 960px. O calendário mostra uma instrução de rolagem no celular. As classes responsivas legadas de Tailwind continuam presentes em outras superfícies: sm 640px, md 768px e lg 1024px; as regras específicas de gestao.css governam os comportamentos acima.

O ritmo usa passos compactos de 6–16px e separações de 24–28px. A navegação tem altura mínima de 44px; campos e ações dentro do conteúdo de gestão, 38px. Respostas de checklist mantêm mínimo de 105px.

## Elevation & Depth

A gestão é predominantemente plana: bordas e fundos distinguem painéis, colunas e cartões; sombras pequenas e médias são removidas do conteúdo. O operador mantém resposta tátil nos botões de inspeção, com sombra de repouso e deslocamento ao pressionar. Modais mantêm as sombras maiores já existentes e sobreposição grafite translúcida.

As respostas do checklist usam sombra 0 4px 6px #24334420; botões industriais pressionados usam inset 0 3px 6px rgba(0,0,0,0.35). As respostas de inspeção têm sombra pressionada específica inset 0 4px 8px rgba(0,0,0,0.4). O fundo modal é #24334480. Esses valores e transições ficam no sidecar, fora do esquema de tokens YAML.

A pulsação do botão SOS de cabeçalho está desativada; a gravação de áudio ainda sinaliza atividade. A preferência por movimento reduzido desativa animações e transições globalmente.

## Shapes

Controles de gestão têm cantos discretos; cartões usam card e painéis usam panel. O resumo de prioridades usa summary. Etiquetas compactas usam chip, contadores usam pill e modais existentes podem usar modal. Bordas comuns medem 1px; marcadores superiores de coluna medem 2px. A forma arredondada não deve apagar a hierarquia entre uma etiqueta, uma ação e um painel.

## Components

### Buttons

O envio final do relatório é sólido, cobre com texto branco, preenchimento de 14px, raio panel, texto de 1.125rem e peso 700. O hover escurece o fundo; a classe industrial desloca a ação ao pressionar. Ações neutras como Atualizar usam branco, borda line e raio control. Desabilitados têm opacidade .5 e cursor de indisponibilidade. Respostas conforme/não conforme usam verde/vermelho sólido e mantêm 105px de altura mínima.

### Chips

A prioridade urgente usa vermelho translúcido, texto danger e cantos chip. A palavra de prioridade permanece visível. Contadores usam cápsulas neutras; etiquetas de unidade preservam os estilos semânticos existentes. Etiquetas informativas não recebem comportamento de botão.

### Cards / Containers

Ordens usam fundo branco, borda discreta, raio card e 14px de preenchimento. O hover realça a borda, sem elevar o cartão. A etapa é alterada por select com nome acessível, colocado abaixo do equipamento e em toda a largura. As colunas têm fundo cinza próprio, raio panel e barra superior da etapa.

### Inputs / Fields

Busca de checklists e frota usa campo branco, borda field-line, raio card, ícone à esquerda e nome acessível descritivo. Filtros possuem rótulos visíveis, limpeza e contagem de resultados. Foco global usa contorno de 3px em cobre com deslocamento de 3px, inclusive em elementos que conservam estilos de foco locais.

### Navigation

A aba atual usa fundo accent-soft, texto cobre escuro e peso 700, marcada com aria-current="page". Demais abas usam muted e hover neutro. A faixa passa de vertical para horizontal em até 1000px. O acesso à gestão no cabeçalho mantém aria-label mesmo quando seu texto visual é ocultado.

### Priority Summary

O resumo agrupa contagens de ordens urgentes, ordens abertas e acesso aos chamados SOS em superfície quente com borda e links sublinhados. Os valores vêm dos dados carregados; exemplos de documentação não representam a situação real da frota.

## Do's and Don'ts

### Do:

- Do preservar foco visível, nomes acessíveis e ampliação de texto.
- Do usar Inter e algarismos tabulares no conteúdo de gestão.
- Do manter respostas do checklist com altura mínima de 105px.
- Do acompanhar estados com texto e cores semânticas.
- Do conferir telas estreitas com filtros, tabelas e calendário reais.

### Don't:

- Don't reintroduzir gradientes nos botões de resposta do checklist.
- Don't usar sombras pequenas ou médias como estrutura do painel de gestão.
- Don't esconder o estado de rede no celular.
- Don't aplicar a fonte monoespaçada indiscriminadamente em novas telas.
- Don't transformar exemplos de documentação em dados operacionais.

