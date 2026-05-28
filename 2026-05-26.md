# Changelog — 26/05/2026

## Edge Functions

- **Resolução de operadoras e prestadores** via mapeamento `side_effects` em JSON dos templates.
- **Compatibilidade de fontes de dados**: tratamento equivalente de imagens para lookup no banco.

## Responsividade Mobile — Painel Admin

- **`AdminMobileCard` + `AdminMobileField`**: componente compartilhado para padronizar exibição de dados no mobile.
- **Listagens** (Usuários, Operadoras, Planos, Prestadores, Templates) alternam entre cards (mobile) e tabela (desktop), sem scroll horizontal.
- **Tabs de formulários** (Operadora, Plano) empilham vertical no mobile.
- **Botões e headers** padronizados com `flex-col` / `w-full` no mobile.
- **`AdminLayout`, `AdminPageHeader`, `AdminDashboard`, `AdminTemplateEditor` e `ImageGalleryManager`** ajustados.
- **Desktop preservado** sem alterações.
