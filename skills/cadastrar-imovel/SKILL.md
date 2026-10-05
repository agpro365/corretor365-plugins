---
name: cadastrar-imovel
description: Monta o cadastro de um imóvel novo no corretor365 a partir de um texto (a mensagem do proprietário, um anúncio, anotações de visita). Use quando pedirem para cadastrar, criar ou subir um imóvel novo.
---

# Cadastrar imóvel novo no corretor365

Você transforma um texto em cadastro. O imóvel **não é criado na hora**: o cadastro vira uma sugestão, e uma pessoa
da imobiliária clica em *Criar como rascunho* no painel. Ele nasce **Rascunho**, sem fotos, fora do site até alguém
publicar.

## Como trabalhar

1. `get_account` primeiro: confirma a conta e que esta conexão pode sugerir imóveis.
2. Se o texto der o bairro, confira com `search_properties` se a imobiliária já não tem esse imóvel (mesmo bairro,
   mesmos quartos, área e preço parecidos). O painel também avisa, mas perguntar antes poupa trabalho.
3. Mande `propose_new_property` com:
   - `title` — o título do envio ("Novo imóvel na Rua X");
   - `property` — os campos do cadastro em inglês e preços **em reais**: `title`, `description`, `property_type`,
     `transaction`, `sale_price_brl` ou `rent_price_brl`, `condo_fee_brl`, `property_tax_brl`, `bedrooms`, `suites`,
     `bathrooms`, `parking_spaces`, `private_area_m2`, `street`, `street_number`, `neighborhood`, `city`, `state`,
     `postal_code`, `amenities`…;
   - `reason` — de onde veio o cadastro.
4. Mostre o link do envio e os avisos que a ferramenta devolver (campos em branco, imóvel parecido, cota).

## Regras

- **Deixe de fora o que o texto não diz.** Campo em branco é melhor que campo inventado: o painel mostra o que
  faltou para a pessoa completar.
- Não ponha contato do proprietário (telefone, e-mail, CPF) em nenhum campo — documento é recusado.
- O endereço exato fica escondido no site até alguém decidir mostrar.
