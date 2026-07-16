---
title: Formulário público de inscrição
parent: Módulos
nav_order: 8
---

# Formulário público de inscrição

É a tela que o **responsável pela inscrição** usa para inscrever um grupo. Ela aparece na página do evento, por shortcode ou na página temática, sempre com a **logo e as cores do evento**.

![Formulário público de inscrição com preço ao vivo](/assets/screenshots/form-publico.png)

## Como o responsável se inscreve

1. **Dados do responsável** — nome e e-mail (obrigatórios), telefone e organização.
2. **Participantes** — o responsável adiciona um card por participante e preenche os campos que você configurou. Pode adicionar e remover participantes livremente.
3. **Preço ao vivo** — a cada participante, o **preço unitário e o total** são recalculados na hora, e a **faixa ativa** aparece destacada na tabela de preços. Se o evento usa **modalidades**, o resumo mostra o detalhamento por modalidade. Se o evento usa **preço por lote (data)**, o formulário mostra a lista de **lotes** com o **lote atual destacado**, e cobra o preço desse lote por inscrito.

![Formulário público de um evento com preço por lote de data](/assets/screenshots/form-publico-lotes.png)
4. **Consentimento** — o responsável marca o consentimento de tratamento de dados (com link para a sua política). Se o evento habilitar, há também a opção de **networking** (que libera o vCard no QR da credencial).
5. **Checkout** — ao confirmar, o formulário valida os dados (incluindo CPF e e-mail), leva a inscrição ao carrinho e segue **direto para o checkout** do WooCommerce.

## Importar participantes por planilha

Em vez de digitar um a um, o responsável pode **importar uma planilha**:

- baixa um **modelo** de planilha com as colunas certas;
- preenche em CSV ou XLSX;
- faz o **upload** — os cards de participante são preenchidos automaticamente.

{: .tip }
> **A importação é o que viabiliza grupos grandes**
>
> Uma empresa que inscreve 80 funcionários não vai digitar 80 vezes. Deixe o modelo de planilha visível e explique nos seus canais que dá para importar — isso reduz o abandono do formulário em inscrições grandes.

## Disponibilidade

Se as **inscrições estiverem fechadas** ou o evento **esgotado**, o formulário informa a situação. No caso de capacidade atingida com a política de excedente, ele **avisa** que a inscrição entrará como excedente e permite prosseguir.

{: .note }
> **Validação protege os dados:** campos obrigatórios, CPF e e-mail são validados antes de seguir para o pagamento, com mensagens de erro por campo. Isso evita inscrições incompletas e reduz retrabalho depois.
