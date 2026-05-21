# Atualizações – 21/05/2026

## 1. Painel Administrativo + Permissões
- Criado painel `/admin` com dashboard, gerenciamento de usuários, templates, operadoras, planos e prestadores.
- Implementado controle de acesso por papéis (RBAC): **Admin** e **Editor (criador de artes)**.
- Criada tabela `user_roles` + função `has_role()` para evitar escalada de privilégios via RLS.
- Editor mantém acesso a Gallery, Editor e Histórico próprio, mas **não acessa o painel admin**.
- Rotas utilitárias (`/seed`, `/normalize`, `/update-template`) agora restritas a admin.

## 2. Correções de Segurança
- **XSS em templates/artes**: adicionada sanitização de HTML com DOMPurify antes de injetar conteúdo em `innerHTML`.
- **Verificação de role no cliente**: corrigido — agora a verificação de admin usa `user_roles` + RLS no banco, não só o frontend.

## 3. CRUD Completo de Catálogo
- Adicionados formulários de cadastro/edição para **Operadoras**, **Planos** e **Prestadores**.
- **Plano → Rede Credenciada**: gestão de hospitais/clínicas vinculados ao plano com nível de relevância.
- **Prestador → Galeria de Imagens**: upload múltiplo de fotos (fachada, interior, logo, outros) com ordenação por prioridade.
- Criado bucket `prestadores` no Storage com policies de leitura pública e escrita apenas para admin.

## 4. Erros Corrigidos
- **Acesso negado ao painel admin** — mesmo com `papel='admin'` em `perfis`, faltava registro na tabela `user_roles`. Corrigido com SQL de sincronização.
- **Link de redefinição de senha redirecionando para home** — template de e-mail no Supabase usava `{{ .SiteURL }}` em vez de `{{ .ConfirmationURL }}`; também faltava `/reset-password` nas URLs de redirecionamento permitidas. Orientada configuração no painel Supabase.

## 5. Melhorias no Cadastro de Prestadores
- **Autofill por CEP**: ao preencher o CEP, o sistema busca no ViaCEP e preenche endereço, bairro e cidade automaticamente.
- **Máscara de telefone**: formato `(00) 0000-0000` aplicado no campo Telefone.
- **Filtro por cidade** na listagem de prestadores do painel admin.

## 6. Separação de Templates por Categoria
- Adicionada coluna `categoria` na tabela `templates` (valores: `ADESAO`, `EMPRESARIAL`).
- Home (Gallery) agora exibe **duas seções empilhadas**: Templates para Adesão e Templates para Empresarial.
- Painel admin permite reclassificar a categoria de cada template inline.

---

## Migrações Manuais Aplicadas (SQL Editor Supabase)
1. `migracao_user_roles.sql` — enum, tabela, função `has_role()`, policies RLS e sincronização de perfis.
2. Criação do bucket `prestadores` e policies de Storage.
3. Adição do enum `template_categoria` e coluna `categoria` em `templates`.
