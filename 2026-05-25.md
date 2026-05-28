# Changelog — 25/05/2026

## Arquitetura — Estilos Compartilhados e Templates

- **Tabela `estilos`** desacoplada de `templates` (`id_estilo` FK).
- **CSS imune ao PurgeCSS** via injeção dinâmica.
- **Escopo de CSS**: `body`/`html` reescritos para `.template-preview`, evitando vazamento de estilos no app.
- **Pipeline de geração de imagem** (`html-to-image`) com inlining de CSS e timeout de fontes.
- **Armazenamento de artes geradas** via blob → Storage (path por `user_id`) → referência em `artes_geradas`.

## Edge Functions

- **Resolução de operadoras e prestadores** via mapeamento `side_effects` em JSON dos templates.
- **Compatibilidade de fontes de dados**: tratamento equivalente de imagens para lookup no banco.
