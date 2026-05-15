# Pulso — Site institucional

Single-page institucional da Pulso. Stack: HTML puro + Google Fonts (Instrument Serif + Geist). Zero dependência de build.

## Stack

- `index.html` — todo o site em um arquivo
- CSS embutido no `<head>` (sem arquivo externo)
- Fonts via CDN do Google Fonts
- Animações via IntersectionObserver (JS no rodapé do arquivo)
- Sem JS framework, sem bundler, sem build step

## Deploy — caminho mais curto (≈ 10 min)

### 1. Subir pro GitHub

```bash
git init
git add index.html README.md
git commit -m "first commit — site institucional Pulso"
git branch -M main
git remote add origin git@github.com:SEU_USUARIO/pulso-site.git
git push -u origin main
```

### 2. Conectar Vercel ao repo

1. Acesse https://vercel.com → New Project
2. Import o repo `pulso-site`
3. Framework Preset: **Other**
4. Root Directory: `./`
5. Build Command: deixar vazio
6. Output Directory: deixar vazio (Vercel detecta `index.html` automaticamente)
7. Deploy

Em ~30 segundos sai uma URL `pulso-site-xxx.vercel.app` — confere se o site está OK.

### 3. Apontar `usepulso.org` pro Vercel

No painel da Vercel, no projeto:

1. Settings → Domains → Add
2. Digite `usepulso.org` e também `www.usepulso.org`
3. Vercel mostra os registros DNS que você precisa adicionar:
   - **A record** no apex `@` apontando pro IP da Vercel
   - **CNAME** em `www` apontando pra `cname.vercel-dns.com`
4. No seu provedor de DNS (Cloudflare, Registro.br, Namecheap, etc), adicione esses dois registros

**IMPORTANTE — sobre conflito com `proposta.usepulso.org`:**
O subdomínio `proposta` continua funcionando intacto. Você está só adicionando entradas DNS pro apex (`usepulso.org`) e pro `www`. As entradas do `proposta` já existem na sua zona DNS e não são tocadas.

### 4. Esperar DNS propagar

Tipicamente 5–30 min. Vercel emite o certificado SSL automaticamente.

## Pontos pendentes (preencher quando estiver pronto)

Procurar e substituir no `index.html`:

1. **Link do WhatsApp** — buscar por `id="whatsCta"` e trocar `href="#"` por:
   `href="https://wa.me/55SEUNUMERO?text=Vim%20pelo%20site%20da%20Pulso"`

2. **Favicon definitivo** — substituir a tag `<link rel="icon" ...>` por um arquivo real (ex: `favicon.ico` na raiz)

3. **Imagem Open Graph** — adicionar `<meta property="og:image" content="https://usepulso.org/og.png">` quando tiver a arte de compartilhamento

## Editar conteúdo

Tudo está em `index.html`. As seções estão comentadas com `<!-- ========== NOME ========== -->`. Basta achar a seção e editar o texto.

## Performance

Lighthouse esperado: 95+ em todas as métricas. Sem imagens pesadas, sem JS bloqueante, fonts com `display=swap`.
