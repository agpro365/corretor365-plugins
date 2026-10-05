---
name: ajustar-precos
description: Sugere reajustes de preço de venda ou de aluguel nos imóveis da imobiliária no corretor365, a partir de critérios que a pessoa der (dias no acervo, falta de leads, bairro, faixa de preço). Use quando pedirem para baixar, subir ou revisar preços.
---

# Ajustar preços no corretor365

Você prepara reajustes de preço para a imobiliária revisar. Nada muda sozinho: o reajuste vira **sugestão** no
painel do corretor365, e uma pessoa aplica.

## Como trabalhar

1. `get_account` primeiro, para saber o que esta conexão pode fazer.
2. Ache os imóveis com `search_properties`. Os critérios mais úteis: `min_days_listed` (há quanto tempo está no
   acervo), visitas e leads em 30 dias, bairro, tipo e faixa de preço.
3. Confira cada imóvel com `get_property` antes de sugerir — o preço de hoje é o ponto de partida.
4. Mande **um envio** com `propose_property_changes`, um item por imóvel, com o campo `sale_price_brl` (venda) ou
   `rent_price_brl` (aluguel). **Preços em reais**, sem centavos quebrados: arredonde para um valor de anúncio
   (R$ 845.000, não R$ 844.873,12).
5. Em cada item, o motivo em uma frase ("No acervo há 132 dias, sem lead em 30 dias").
6. Mostre o link do envio que a ferramenta devolve.

## Cuidados

- Mudança de mais de 20%, ou preço abaixo do piso, chega ao painel **com alerta** e é conferida um a um. Se a pessoa
  pediu algo grande assim, avise no resumo do envio.
- Não mexa em `price_display` (como o preço aparece) nem na situação do imóvel a não ser que peçam.
- Lançamento com plantas tem o preço vindo das plantas: o painel recusa o reajuste no anúncio e diz onde mudar.
