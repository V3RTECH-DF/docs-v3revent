---
title: Formulário público de inscrição
parent: Módulos
nav_order: 8
---

# Formulário público de inscrição

É a tela que o participante (ou o responsável por um grupo) usa para se inscrever. Ela aparece na página do evento, por shortcode ou na página temática, sempre com a **logo e as cores do evento**.

![Formulário público de inscrição com preço ao vivo](/assets/screenshots/form-publico.png)

## Individual ou em grupo?

Cada evento define um **[Tipo de inscrição](/modulos/editor-evento/)** que controla se o formulário pede os **Dados do Responsável pela Inscrição** (a pessoa que inscreve um grupo):

- **O participante escolhe** (padrão): no topo do formulário aparece a pergunta **"Para quem é esta inscrição?"**. Em **"Somente para mim"**, a seção do responsável fica oculta; em **"Para um grupo de pessoas"**, ela aparece.
- **Somente individual**: a seção do responsável **não aparece** — o contato da inscrição é o próprio participante.
- **Sempre em grupo**: a seção do responsável aparece direto, como um passo obrigatório.

![Formulário com a pergunta "Para quem é esta inscrição?" e o responsável oculto](/assets/screenshots/form-publico-escopo.png)

{: .note }
> Quando não há responsável (inscrição individual), o **e-mail de confirmação e o recibo** usam o nome e o e-mail informados no **checkout** — ou seja, os do próprio participante.

## Como se inscrever

1. **Dados do responsável** *(quando aplicável)* — nome e e-mail (obrigatórios), telefone e organização.
2. **Participantes** — o responsável adiciona um card por participante e preenche os campos que você configurou. Pode adicionar e remover participantes livremente.
3. **Preço ao vivo** — a cada participante, o **preço unitário e o total** são recalculados na hora, e a **faixa ativa** aparece destacada na tabela de preços. Se o evento usa **modalidades**, o resumo mostra o detalhamento por modalidade. Se o evento usa **preço por lote (data)**, o formulário mostra a lista de **lotes** com o **lote atual destacado**, e cobra o preço desse lote por inscrito.

{: .note }
> **"Valor base" quando o preço varia.** Se a **modalidade** e/ou a **quantidade** afetam o valor, os preços exibidos na tabela aparecem como **"Valor base"**, com um aviso de que o valor final **varia conforme a categoria e/ou a quantidade** de inscritos. O **valor efetivo** de cada um aparece no **resumo** depois que a pessoa escolhe a categoria e adiciona os participantes.

![Formulário público de um evento com preço por lote de data](/assets/screenshots/form-publico-lotes.png)
4. **Consentimento** — o responsável marca o consentimento de tratamento de dados (com link para a sua política). Se o evento habilitar, há também a opção de **networking** (que libera o vCard no QR da credencial).
5. **Checkout** — ao confirmar, o formulário valida os dados (incluindo CPF e e-mail), leva a inscrição ao carrinho e segue **direto para o checkout** do WooCommerce.

{: .tip }
> **Tem um cupom de desconto?** No checkout, o participante pode inserir o código no campo de cupom e o desconto é abatido do total. Veja como criar e restringir cupons em **[Descontos com cupom](/guia-do-gestor/descontos-com-cupom/)**.

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
