# Checklist 5S e Gestão Industrial de Frotas — JPatrício

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Operadores de chão de fábrica preenchem inspeções com apoio de voz e controles grandes para toque com luvas. Gestores acompanham Matriz e Filial. A prioridade diária confirmada é tratar pendências críticas e manutenções, seguida de histórico e frota.

## Product Purpose

Registrar inspeções 5S, identificar defeitos e acompanhar disponibilidade e manutenção de máquinas e veículos.

## Operating Context

Aplicação em português brasileiro, usada em computadores, tablets e celulares. Operador segue etapas; gestor acessa painel com indicadores, checklists, manutenção em Kanban/calendário, frota e chamados SOS.

## Capabilities and Constraints

HTML, JavaScript nativo, Tailwind CDN, FontAwesome 6 e Supabase JS v2. Preservar os fluxos e integrações existentes, testar sintaxe antes de commit e evitar dependências pesadas. Pasta oficial: C:\Users\ricar\Documents\JPatricio\checklist. Atualizações devem ser registradas por commit e enviadas ao repositório GitHub ricardomosi/checklist.

O código atual usa maquinas, maquina_especificacoes, checklists, checklist_observacoes, ordens_manutencao e chamados_emergencia; o onboarding não substitui a estrutura efetivamente implementada. O fluxo de inspeção de veículos ainda aparece como Em breve.

## Brand Commitments

JPatrício. O usuário solicitou visual claro, profissional, tipografia legível, cores consistentes e eliminação da estética genérica de IA.

## Evidence on Hand

index.html e ativos em imagens/. Onboarding fornecido pelo usuário e interface executável local. Não inventar dados operacionais.

## Product Principles

- Expor urgências e próximos passos de manutenção.
- Preservar rapidez e acessibilidade no chão de fábrica.
- Tornar filtros, unidades e estados inequívocos.
- Manter documentação compartilhável entre Codex e Antigravity.

## Accessibility & Inclusion

Manter respostas de checklist com altura mínima de 105px, apoio de voz e acesso por teclado. Permitir zoom e ajustar tamanho de texto sem perder controles.
