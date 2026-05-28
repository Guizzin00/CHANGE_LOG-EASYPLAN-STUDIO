# Changelog — 27/05/2026

## Hub de Objetivos + Rascunhos Editáveis

> **Migration:** `2026-05-27-hub-objetivos-e-rascunhos.sql`

- **Colunas `categoria_objetivo` e `modo`** em `templates`:
  - `categoria_objetivo`: hospitais, rede_credenciada, preco, entidades, diferenciais, empresarial
  - `modo`: `unico` | `destaques`
- **Index** `idx_templates_categoria_objetivo`.
- **Nova tabela `rascunhos_templates`**:
  - `id`, `id_perfil`, `id_template`, `nome`, `parametros_utilizados` (jsonb), `created_at`, `modificado_em`
- **GRANTs** para `authenticated`/`service_role` + **RLS** por `id_perfil = auth.uid()` (`SELECT`/`INSERT`/`UPDATE`/`DELETE`).
- **Hook `useRascunhos`** para CRUD.
- **Home reorganizada** com `ObjetivoCard` e `RascunhosList`.

## Responsividade Mobile — Painel Admin

- **`AdminMobileCard` + `AdminMobileField`**: componente compartilhado para padronizar exibição de dados no mobile.
- **Listagens** (Usuários, Operadoras, Planos, Prestadores, Templates) alternam entre cards (mobile) e tabela (desktop), sem scroll horizontal.
- **Tabs de formulários** (Operadora, Plano) empilham vertical no mobile.
- **Botões e headers** padronizados com `flex-col` / `w-full` no mobile.
- **`AdminLayout`, `AdminPageHeader`, `AdminDashboard`, `AdminTemplateEditor` e `ImageGalleryManager`** ajustados.
- **Desktop preservado** sem alterações.
