# Revisão inicial — 12/09/2026

## Escopo e direção confirmados

Interface clara e profissional para gestores; prioridade em pendências críticas e manutenção, seguida de histórico e frota. Preservar fluxo de operador e controles grandes. Análise inicial em 1280 × 720; implementação direta autorizada pelo usuário e validação em desktop e celular realizadas em 13/09/2026.

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

## Implementação visual

Tema claro aplicado ao operador, gestor e modais. Menu lateral em desktop e faixa rolável no celular; Manutenções abre por padrão. Ordens urgentes vêm primeiro dentro da etapa. Resumo de urgências e acesso ao SOS ficam acima do quadro.

Tipografia de interface com escala em rem, botão A+ persistente, zoom liberado, foco visível, cartões de frota acionáveis por teclado e redução de movimento conforme preferência do dispositivo. Filtros de histórico e frota receberam rótulos e ação de limpeza. Calendário mantém dias legíveis com rolagem horizontal própria no celular.

Troca de abas usa o cache carregado; Atualizar refaz as consultas. Erros retornados pelo banco agora aparecem com opção de tentar novamente. Indicadores sem restrição incluem todo o histórico carregado, inclusive nomes antigos, e ausência de checklists não aparece como 100% de conformidade.

Verificações: JavaScript analisado pelo Node, acesso por PIN, navegação, Kanban/calendário, filtros e reset, buscas sem acento, aumento/restauração de texto e abertura do perfil técnico. Capturas locais em .impeccable/review/. Nenhuma operação de gravação no Supabase foi usada para teste.

## Melhorias futuras identificadas

Mapear nomes históricos a IDs de equipamento para filtros específicos confiáveis; ampliar/paginar o histórico além dos limites de consulta existentes; tornar autorizações de gestores independentes do PIN no frontend; testar sincronização offline com falhas parciais antes de expandir esse fluxo. Esses itens exigem trabalho de dados/backend além da reformulação visual.
