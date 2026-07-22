# Pilastra — Site institucional

Site da Pilastra: infraestrutura de IA privada e conforme para setores regulados no Brasil (primeira vertical: educação).

## Estrutura

Site **estático, sem build** — HTML + CSS + JS vanilla, um arquivo por página. Não há dependências, bundler ou etapa de compilação.

```
index.html                    → home (roteador: problema em dados + 3 caminhos)
plataforma/index.html         → produto para escolas (3 telas, whitelabel, piloto, FAQ)
api/index.html                → produto para edtechs (endpoint, pseudonimização, bundle contratual)
confianca/index.html          → Central de Confiança (7 perguntas, documentos, formulário, DPO)
confianca/obrigado/index.html → agradecimento do pacote de conformidade (noindex)
obrigado/index.html           → agradecimento genérico dos formulários (noindex)
politica-de-privacidade/      → Política de Privacidade (v1.2)
privacidade/                  → redirect legado para a política (noindex)
robots.txt                    → liberação explícita para crawlers de IA + sitemap
sitemap.xml                   → sitemap
llms.txt                      → resumo estruturado para agentes de IA
llms-full.txt                 → conteúdo completo do site em Markdown (para agentes)
og-image.png                  → imagem social (Open Graph / Twitter Card, 1200×630)
```

## Deploy

Hospedado na **Cloudflare Pages**, com deploy automático a partir deste repositório:

- Todo push na branch `main` → publica em produção.
- Todo push em outra branch / PR → gera URL de preview automática.

**Configuração do projeto na Cloudflare Pages:** framework = `None`, build command = *(vazio)*, output directory = `/` (raiz).

## Editando

Como não há build, basta editar os HTMLs e commitar. Cada página carrega seu próprio CSS (design system duplicado por arquivo) — ao mudar nav, footer ou tokens, replicar em todas as páginas. Pontos de atenção:

- **Copy factual:** não afirmar que "a lei exige dado no Brasil" (é diferencial, não obrigação); não usar "certificado/selo"; conformidade = "adequação" e "redução de risco". Sem preços em nenhuma página. Não citar concorrentes nominalmente.
- **Estatísticas:** fontes oficiais — TIC Educação 2024 (Cetic.br/NIC.br) e UNESCO (2023). Não usar dados sem fonte.
- **Formulários (home, /plataforma, /api, /confianca):** enviam via FormSubmit para contato@pilastra.com.br (sem backend), com `_subject` distinto por página para triagem e redirect para /obrigado/ (ou /confianca/obrigado/ no caso do pacote de conformidade). A linha correspondente na Política de Privacidade (seção 5) é obrigatória — formulários não vão ao ar sem ela.
- **llms.txt / llms-full.txt:** quando o conteúdo do site mudar, atualizar esses arquivos também — são a porta de entrada dos agentes de IA.
- **JSON-LD** (no `<head>`): Organization na home, FAQPage na /confianca e na /plataforma — manter em sincronia com a copy.

## Contato

contato@pilastra.com.br · WhatsApp +55 11 98705-0864
Vrummm Tecnologia LTDA · CNPJ 37.442.535/0001-22
