---
title: Descontos com cupom
parent: Guia do gestor
nav_order: 4
---

# Descontos com cupom

O V3REvent usa o **checkout padrão do WooCommerce** para receber o pagamento das inscrições. Por isso, os **cupons de desconto do WooCommerce funcionam normalmente** nas inscrições — você cria o cupom uma vez e o participante aplica o código no momento de finalizar.

Serve para early bird, cupom de parceiro/patrocinador, cortesia para um grupo específico, ou qualquer promoção por tempo limitado.

{: .note }
> O cupom incide sobre o **valor da inscrição já calculado** pelo V3REvent — ou seja, sobre o total depois de aplicadas as faixas de quantidade, o lote de data ou a modalidade. Um cupom de 10% num total de R$ 118,00 desconta R$ 11,80.

## Como criar um cupom (você, gestor)

Os cupons ficam no WooCommerce, não numa tela do V3REvent.

1. No menu do WordPress, abra **Marketing → Cupons** (em algumas versões, **WooCommerce → Cupons**) e clique em **Adicionar cupom**.
2. Dê um **código** ao cupom (ex.: `EVENTO10`) — é o que o participante vai digitar. O código **não diferencia maiúsculas de minúsculas**.
3. Em **Dados do cupom → Geral**, escolha o **Tipo de desconto** e o **Valor**:
   - **Desconto em porcentagem** — um percentual sobre o total da inscrição (ex.: 10%).
   - **Desconto fixo no carrinho** — um valor em reais abatido do total.
   - *(Desconto fixo no produto também existe, mas para inscrições o mais comum é porcentagem ou fixo no carrinho.)*
4. Opcionalmente, defina a **Data de expiração**.

![Criação de um cupom no WooCommerce: código, tipo de desconto em porcentagem e valor](/assets/screenshots/cupom-criar.png)

5. Clique em **Publicar** (ou **Atualizar**).

## Restringir o cupom a um evento

Por padrão, o cupom vale para **qualquer** compra na loja. Para limitá-lo, use a aba **Dados do cupom → Restrição de uso**:

![Aba Restrição de uso do cupom, com limites por valor, produtos, categorias e e-mails](/assets/screenshots/cupom-restricao.png)

- **Gasto mínimo / máximo** — condiciona o cupom a uma faixa de valor.
- **Categorias de produto** — o jeito mais prático de amarrar o cupom a eventos: se você agrupa os eventos numa categoria de produto, informe-a aqui e o cupom só valerá para inscrições daquela categoria.
- **E-mails permitidos** — restringe o uso a endereços específicos (útil para cortesias nominais).

{: .tip }
> **Por que não restringir “por produto”?**
>
> Cada evento tem um produto do WooCommerce **oculto do catálogo**, criado automaticamente pelo V3REvent. Dá para restringir por ele no campo **Produtos**, mas você precisaria saber o produto certo. Na prática, **cupom geral** (para todos os eventos) ou **por categoria** é mais simples de manter.

Em **Limites de uso** você ainda pode definir quantas vezes o cupom pode ser usado no total e por cliente.

## Como o participante aplica o cupom

No **checkout** — a tela que aparece depois que o participante preenche o formulário de inscrição — há um campo de cupom:

- No checkout em blocos: **Adicionar cupons**.
- No checkout clássico: **“Tem um cupom? Clique aqui para inserir seu código.”**

O participante digita o código e clica em **Aplicar**. O desconto aparece na hora no resumo do pedido, e o total é recalculado:

![Resumo do pedido no checkout com o cupom aplicado e o desconto abatido do total](/assets/screenshots/cupom-checkout.png)

## Pré-requisitos e cuidados

- **Cupons precisam estar habilitados** no WooCommerce (**WooCommerce → Configurações → Geral → Ativar o uso de cupons**). Se o campo de cupom não aparece no checkout, comece por aqui.
- **Teste antes de divulgar.** Faça uma inscrição de ponta a ponta com dados fictícios, aplique o cupom e confira se o desconto e o total batem — do mesmo jeito que você já testa preço e e-mails ([Antes do evento](/guia-do-gestor/antes-do-evento/)).
- **Combinação de cupons e “uso individual”**: se marcar **Uso individual apenas**, aquele cupom não poderá ser somado a outros.

{: .note }
> O desconto do cupom fica registrado no **pedido do WooCommerce**. Nos relatórios de receita do V3REvent, a inscrição entra com o valor efetivamente cobrado.
