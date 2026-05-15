# Pulso Site — Contexto pro Claude Code

## O que é
Site institucional da Pulso, aceleradora comercial pra saúde estética premium (implanto, plástica, dermato, dentista high-ticket).
Stack: HTML único + Google Fonts CDN. Zero build.
Deploy: GitHub → Vercel → usepulso.org. Push na main = deploy automático em ~30s.

## Regras invioláveis
1. Edite SÓ o index.html. Não crie arquivos novos sem pedir.
2. NÃO mude paleta/tipografia sem pedido explícito. Cores: bg #0A0A0A, accent #FF2D5F, texto #FAFAF7. Fonts: Instrument Serif + Geist.
3. NÃO mexa nos números do caso real (Médica de Blefaroplastia): +R$300k em 4 semanas, R$5k anúncio, R$4k comercial 01.
4. Mantenha sempre "12 semanas" (nunca "90 dias").
5. Mantenha a ressalva do caso: "Resultados variam conforme estrutura, especialidade e mercado. O que se mantém é a metodologia."
6. NÃO atribua a Pulso credenciais da AdvHub. USP-RP e "+200 negócios" são do Sâmeque e podem ser usados.
7. Nunca rode rm, DROP, ou qualquer comando destrutivo sem confirmar 2x.

## Fluxo padrão de edição
1. Sâmeque pede mudança em linguagem natural
2. Edita o index.html cirurgicamente
3. Mostra o diff
4. Quando aprovado: git add → commit (mensagem curta, verbo no infinitivo, ≤60 chars) → push
5. Vercel redeploya automático em ~30s

## Estrutura do index.html
Seções marcadas com `<!-- ========== NOME ========== -->`:
Hero, Posicionamento (01), Para quem é (02), Método (03 · 4 pilares), Caso real (04), Credibilidade (05 · +200), Founder (06 · Sâmeque), Final CTA (07 · WhatsApp), Footer.

## Pendências
- href="#" no botão id="whatsCta" → trocar pelo wa.me real
- Favicon real
- Imagem og:image
