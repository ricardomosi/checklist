# Revisão inicial — 12/09/2026

## Escopo e direção confirmados

Interface clara e profissional para gestores; prioridade em pendências críticas e manutenção, seguida de histórico e frota. Preservar fluxo de operador e controles grandes. Inspeção realizada no navegador local em 1280 × 720, nas abas Indicadores, Checklists, Manutenções e Frotas. Esta é a análise inicial: o redesign e a validação responsiva ainda não estão concluídos.

## Problemas encontrados

- Títulos, filtros e abas competem no mesmo cabeçalho. Separar navegação e área de trabalho.
- Textos de 9–11px, excesso de caixa alta e pesos fortes dificultam leitura prolongada.
- Superfícies escuras aninhadas, várias cores decorativas e indicadores pulsantes criam ruído.
- Busca recriava o próprio campo a cada tecla; preservar o campo e atualizar somente os resultados.
- Busca de frota anunciava modelo, mas consultava apenas código, nome e placa.
- Busca literal não encontrava nomes acentuados quando digitados sem acento.
- SOS mostrava ação de conclusão para todos os estados. Exibir pendentes primeiro e distinguir resolvidos.
- Indicadores relacionam históricos por igualdade de código textual. Registros antigos usam outros nomes, excluindo parte dos checklists dos indicadores. É necessário mapear a identidade do equipamento; evitar correspondência aproximada que associe máquinas erradas.
- Filtro de equipamentos do histórico usa a frota atual, sem contemplar todos os nomes históricos.
- Dados do gestor são recarregados a cada troca de aba. Melhorar cache, indicar atualização e tratar erros explícitos retornados pelo Supabase.
- Zoom bloqueado pelo viewport; remover essa restrição na reformulação.

## Correções iniciais

Busca contínua sem remontar o campo, normalização de acentos, inclusão de modelo/marca, escape do valor da busca ao gerar HTML e contagem anunciada para leitores de tela. SOS diferencia chamados resolvidos e não infere que toda a frota esteja normal apenas porque não há chamados.

Verificação: sintaxe JavaScript válida; digitação contínua no navegador manteve foco em ambos os filtros; “eletrica” retornou os dois modelos Elétrica e “damiao” retornou registros de Damião. Revisão independente do diff funcional sem bloqueadores. Não foram realizadas gravações de registros de teste no Supabase.

## Próxima implementação

Aplicar a direção visual escolhida na Impeccable: tema claro, navegação legível, rótulos dos filtros, reset dos filtros, escala de texto ajustável e cores semânticas. Validar todas as abas e modais em desktop e celular. A escolha entre implementação direta e composição visual prévia permanece pendente.
