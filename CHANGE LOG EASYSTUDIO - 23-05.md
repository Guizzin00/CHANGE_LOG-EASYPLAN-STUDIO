# Changelog — 23/05/2026

## Editor — Geração em Lote e Zoom

- **Hooks `useBatchGenerate` e `useBatchGeneratePublicoAlvo`** para gerar várias artes em sequência preservando zoom e posicionamento entre variações.
- **Zoom interativo** no preview (10%-200%) via Ctrl+Scroll com controles fixos.
- **Componente `BatchResultView`** para exibir resultados em lote.
- **Tabela `lotes`** para agrupar artes geradas em batch.

## Editor — Manipulação de Imagem

- **`ImagemAjustavel`, `ImagemAjustavelCombobox` e `ImagemAjustavelPublicoAlvoCombobox`**: imagens com transform inline (zoom/posição) ajustáveis pelo usuário.
- **`ImagemCombobox` / `ImagemPublicoAlvoCombobox`**: seleção restrita a imagens do banco (sem upload livre).
- **`ImagemReadOnly`**: campos `banner_marca` auto-preenchidos do DB.
- **Seletor de imagem por público-alvo** com filtragem em duas etapas.
