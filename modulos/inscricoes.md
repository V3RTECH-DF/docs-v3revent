---
title: Inscrições
parent: Módulos
nav_order: 4
---

# Inscrições

A tela **Inscrições** é a lista de todos os pedidos de inscrição. Aqui você busca, filtra, muda o status e exporta.

![Lista de inscrições com filtros e status editável](/assets/screenshots/inscricoes.png)

{: .note }
> **Precisa das inscrições de um único evento?** Além desta tela geral, cada evento tem a aba **Inscritos** no editor, já filtrada só para aquele evento — com a mesma lista, a mesma troca de status e a mesma exportação (CSV/XLSX/PDF). Veja **[Editor de evento → Inscritos](/modulos/editor-evento/#inscritos)**.

## Filtros e busca

No topo, você filtra por:

- **Evento**;
- **Status** (pendente, confirmada, cancelada);
- **Período** (data de início e fim);
- **Busca** por nome ou e-mail do responsável.

## A tabela

Cada linha é um **participante** — não um pedido. Numa inscrição em grupo, aparece uma linha para **cada pessoa** que vai ao evento, com o **responsável pela inscrição** exibido como uma coluna (é ele quem pagou/preencheu o pedido, mas pode nem ser um dos participantes). Assim você vê quem realmente vai comparecer, sem precisar abrir o pedido no WooCommerce para descobrir os nomes.

Para trocar o **status**, **clique na etiqueta de status** (a "pílula" colorida) da linha: abre um menu com os status disponíveis (Pendente / Confirmada / Cancelada), com o atual marcado. Escolha um e a mudança é **aplicada na hora**.

{: .important }
> **O status é do pedido, não da pessoa.** Ao trocar o status de um participante de uma inscrição em grupo, um aviso deixa claro que a mudança vale para **todos os participantes daquele mesmo pedido** — não dá para confirmar um e deixar outro pendente dentro do mesmo pedido.

Quando um pedido ultrapassou a capacidade do evento, a inscrição aparece **sinalizada como excedente**.

Há também um **link para o pedido no WooCommerce**, para conferir o pagamento e os dados de cobrança.

### Escolher colunas e ordenar

No botão **Colunas**, acima da tabela, você escolhe quais informações aparecem — além das colunas padrão (responsável, evento, valor, data, status), dá para incluir **qualquer campo do formulário do evento**, como a **modalidade** de inscrição. Marque as que quiser ver, clique em **Aplicar**, e a escolha fica **salva para o seu usuário** (vale nas próximas visitas).

![Botão Colunas aberto, com a lista de campos disponíveis para marcar](/assets/screenshots/inscricoes-colunas.png)

Para **ordenar**, clique no **cabeçalho** de qualquer coluna visível — inclusive as que você adicionou. Um clique ordena, outro clique inverte o sentido.

A **exportação** (abaixo) e o **Relatório do evento** respeitam as mesmas colunas escolhidas aqui.

## Status de uma inscrição

| Status | Significado |
|---|---|
| **Pendente** | A inscrição começou, mas o pagamento não foi concluído. |
| **Confirmada** | Pagamento concluído — inscritos registrados e e-mails enviados. |
| **Cancelada** | A inscrição foi cancelada. |

## Exportar

Com um **evento filtrado**, aparecem os botões para exportar a lista em **CSV**, **XLSX** ou **PDF**. Veja também os cortes por presença em **[Relatórios](/modulos/relatorios/)**.

{: .tip }
> **Use a exportação como conferência e backup**
>
> Antes de um evento grande, exporte a lista atual em XLSX e confira nomes, e-mails e quantidades. É mais fácil corrigir um dado agora do que na fila do credenciamento.
