# Pare de Se Abandonar — Landing Page

Landing page de produto digital de **Francielle Lopes**, publicada em produção via **GitHub + Vercel** com domínio **Registro.br**.

- **Produção:** https://franlopes.com.br/pare-de-se-abandonar
- **Stack:** HTML/CSS/JS estático (sem build), hospedagem Vercel (Hobby), SSL automático.

---

## Estrutura

```
.
├── index.html                     # Raiz: redireciona para /pare-de-se-abandonar
├── pare-de-se-abandonar/
│   └── index.html                 # A landing page (produção)
├── privacidade/index.html         # LGPD — Política de Privacidade
├── termos/index.html              # LGPD — Termos de Uso
├── cookies/index.html             # LGPD — Política de Cookies
├── 404.html                       # Página de erro personalizada
├── assets/
│   ├── og.jpg                     # Open Graph 1200×630
│   ├── cover.jpg                  # Capa do e-book
│   ├── icon-192.png / icon-512.png
├── favicon.ico / favicon.svg / apple-touch-icon.png
├── robots.txt
├── sitemap.xml
├── manifest.webmanifest
├── vercel.json                    # Headers de segurança, redirects, cache
├── .gitignore
└── README.md
```

---

## Configuração (IDs e checkout)

Todos os pontos de integração ficam no objeto `window.FL`, no topo de `pare-de-se-abandonar/index.html`:

| Chave | Descrição | Como obter |
|-------|-----------|------------|
| `HOTMART_CHECKOUT_URL` | Link de checkout do produto | Painel Hotmart → Produto → Link de compra |
| `GA4` | ID do Google Analytics 4 (`G-XXXXXXXXXX`) | analytics.google.com |
| `GTM` | ID do Google Tag Manager (`GTM-XXXXXXX`) | tagmanager.google.com |
| `CLARITY` | ID do Microsoft Clarity | clarity.microsoft.com |
| `META_PIXEL` | ID do Meta Pixel | business.facebook.com |

> Enquanto vazios, **nenhum script de rastreamento é carregado** (página permanece limpa e conforme a LGPD).
> Os scripts só são ativados **após o consentimento** do visitante no banner de cookies.

As páginas legais possuem placeholders visíveis (`[DATA]`, `[E-MAIL DE CONTATO]`, `[CPF/CNPJ]`) que devem ser preenchidos antes da divulgação.

---

## Deploy (resumo)

1. **GitHub** — subir este diretório como repositório (branch `main`), criar release `v1.0`.
2. **Vercel** — importar o repositório (framework: *Other* / *Static*), deploy automático a cada push.
3. **Domínio** — adicionar `franlopes.com.br` e `www.franlopes.com.br` no projeto Vercel.
4. **Registro.br** — aplicar exatamente os registros DNS informados pela Vercel (A / CNAME).
5. Aguardar propagação de DNS e emissão automática de SSL.

Redirects e segurança já estão em `vercel.json`:
- `/` → `/pare-de-se-abandonar` (308)
- `www` → domínio principal (configurar no painel Vercel)
- HTTPS forçado + HSTS, CSP, X-Frame-Options, X-Content-Type-Options, Referrer-Policy, Permissions-Policy
- Cache longo e imutável para `/assets/*`

---

## Segurança

- Nenhuma chave, token ou credencial versionada (ver `.gitignore`).
- Compressão Brotli/Gzip automática na Vercel.
- Cabeçalhos de segurança e proteção contra clickjacking e MIME sniffing via `vercel.json`.

## Licença

Conteúdo proprietário © Francielle Lopes. Todos os direitos reservados.
