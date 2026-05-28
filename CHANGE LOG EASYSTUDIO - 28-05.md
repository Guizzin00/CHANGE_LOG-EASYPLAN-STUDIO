# Changelog — 28/05/2026

## Responsividade Mobile — Painel Admin

- **`AdminMobileCard` + `AdminMobileField`**: componente compartilhado para padronizar exibição de dados no mobile.
- **Listagens** (Usuários, Operadoras, Planos, Prestadores, Templates) alternam entre cards (mobile) e tabela (desktop), sem scroll horizontal.
- **Tabs de formulários** (Operadora, Plano) empilham vertical no mobile.
- **Botões e headers** padronizados com `flex-col` / `w-full` no mobile.
- **`AdminLayout`, `AdminPageHeader`, `AdminDashboard`, `AdminTemplateEditor` e `ImageGalleryManager`** ajustados.
- **Desktop preservado** sem alterações.

## Responsividade Mobile — Gallery e Histórico

- **Grid de 2 colunas** no mobile (single column no design original).
- **Cards com padding** (`p-3`) e tipografia reduzidos no mobile.
- **Headers responsivos** (`text-xl` `sm:text-2xl` `md:text-3xl`).
- **Diálogos do Histórico** com `max-w-[95vw]` e botões empilhados em grid no mobile.
- **Container** com `py-4 px-3` no mobile.
- **Desktop inalterado.**
