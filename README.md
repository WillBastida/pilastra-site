# Pilastra — Site institucional

Landing page da Pilastra: infraestrutura de IA privada e conforme para setores regulados no Brasil (primeira vertical: educação).

## Estrutura

Site **estático, sem build** — HTML + CSS + JS vanilla num único arquivo principal. Não há dependências, bundler ou etapa de compilação.

```
index.html        → página única (todo o site)
robots.txt        → liberação explícita para crawlers de IA + sitemap
sitemap.xml       → sitemap
llms.txt          → resumo estruturado para agentes de IA
llms-full.txt     → conteúdo completo do site em Markdown (para agentes)
og-image.png      → imagem social (Open Graph / Twitter Card, 1200×630)
brand/            → símbolo da marca em SVG (versões clara e escura)
```

## Deploy

Hospedado na **Cloudflare Pages**, com deploy automático a partir deste repositório:

- Todo push na branch `main` → publica em produção.
- Todo push em outra branch / PR → gera URL de preview automática.

**Configuração do projeto na Cloudflare Pages:** framework = `None`, build command = *(vazio)*, output directory = `/` (raiz).

## Editando

Como não há build, basta editar `index.html` e commitar. Pontos de atenção:

- **Copy factual:** não afirmar que "a lei exige dado no Brasil" (é diferencial, não obrigação); não usar "certificado/selo"; conformidade = "adequação" e "redução de risco". Sem preços fechados na página.
- **Estatísticas:** fontes oficiais — TIC Educação 2024 (Cetic.br/NIC.br) e UNESCO (2023). Não usar dados sem fonte.
- **llms.txt / llms-full.txt:** quando o conteúdo do site mudar, atualizar esses arquivos também — são a porta de entrada dos agentes de IA.
- **JSON-LD** (no `<head>`): dados estruturados de Organization e FAQ — manter em sincronia com a copy.

## Contato

contato@pilastra.com.br · WhatsApp +55 11 98705-0864
Vrummm Tecnologia LTDA · CNPJ 37.442.535/0001-22
