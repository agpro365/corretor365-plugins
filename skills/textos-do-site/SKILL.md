---
name: textos-do-site
description: Reescreve textos do site da imobiliária no corretor365 — títulos e textos das seções, título das páginas e o SEO (título e descrição para o Google). Use quando pedirem para melhorar a página inicial, o "Sobre nós", chamadas, ou o SEO do site.
---

# Textos do site no corretor365

Você sugere textos para o site da imobiliária. As sugestões entram no **rascunho** do site só quando alguém aplica
no painel, e vão ao ar só quando alguém clica em **Publicar**. Só o proprietário e os administradores mexem no site:
se a ferramenta responder "sem permissão", explique isso e siga com o que for possível.

## Como trabalhar

1. `get_account` primeiro.
2. `list_site_pages` lista as páginas do rascunho com o `page_id` de cada uma.
3. **Leia a página com `get_site_page` antes de sugerir**: ela traz cada seção (`block_id`), os textos que dá para
   mudar (`prop`), o teto de caracteres de cada um e o SEO atual.
4. Mande **um envio** com `propose_site_changes`. Cada item é um alvo:
   - `block_prop` com `block_id` e `prop` — o texto de uma seção;
   - `seo_title` (até 70 caracteres) e `seo_description` (até 160);
   - `page_title`.
5. Mostre o link do envio que a ferramenta devolve.

## Bons textos de site imobiliário

- Diga onde a imobiliária atua e para quem ("Alto padrão no Batel e no Ecoville"), sem promessas vagas.
- SEO: o título com o que se busca e a cidade ("Imóveis de alto padrão em Curitiba | Nome da imobiliária"); a
  descrição com o diferencial em uma frase.
- Texto rico aceita **negrito**, *itálico* e [link](/caminho) — link só para o próprio site, o WhatsApp e as redes.
- Não ponha telefone, e-mail ou WhatsApp nos textos: o contato do site é da imobiliária e não muda por sugestão.
- Os ids das páginas mudam depois de cada Publicar: se a ferramenta disser "página não encontrada", chame
  `list_site_pages` de novo.
