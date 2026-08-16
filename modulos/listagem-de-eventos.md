---
title: Listagem de eventos (shortcode)
parent: Módulos
nav_order: 15
---

# Listagem de eventos (shortcode)

O shortcode `[v3revent_events]` monta, numa página comum do WordPress, uma **lista dos eventos publicados** — em cartões ou em tabela, com filtros de situação da inscrição, modalidade e período, e paginação. Ele não pertence a um evento específico (diferente da maioria dos outros shortcodes do V3REvent): lista **vários** de uma vez.

## Por que isto importa

Por padrão, o único caminho até a página de um evento é o **catálogo da loja do WooCommerce** — e, em muitos sites, esse produto fica **oculto** de propósito (é um evento, não um item à venda). Sem `[v3revent_events]`, quem chega ao seu site sem um link direto simplesmente **não encontra** os eventos.

Cole o shortcode numa página como "Todos os eventos" ou "Nossa agenda" e você tem um caminho público, dentro do próprio site, sem depender da loja nem de o visitante já ter o link de um evento específico.

## Onde colar

No editor do WordPress (Gutenberg), adicione um bloco **Shortcode** e cole `[v3revent_events]` — sozinho ou com os atributos que quiser (veja a lista completa abaixo). Em construtores de página (Elementor, etc.), use o widget/bloco equivalente de "shortcode". Depois, **publique** a página.

## Os dois formatos

Escolha pelo atributo `layout`.

### `cards` (padrão)

Um cartão por evento — imagem, título, data, local, modalidade e um selo de situação ("Abertas", "Em breve", "Encerradas"). É o formato mais visual, bom para uma página de destaque ou para quem navega pelo celular.

```
[v3revent_events]
```

### `table`

Uma tabela com colunas **Evento, Data, Local, Modalidade, Prazo de inscrição e Situação**, mais um botão "Ver evento" em cada linha. O visitante pode **reordenar clicando no cabeçalho** de qualquer coluna ordenável — um clique ordena crescente, outro clique na mesma coluna inverte para decrescente. É o formato mais compacto, bom quando há muitos eventos e o visitante quer comparar rápido.

```
[v3revent_events layout="table"]
```

{: .tip }
> A ordenação que o visitante escolhe na tabela **sobrevive à paginação** — trocar de página não perde a coluna nem o sentido escolhidos.

## Os atributos, um por um

Todos são opcionais — sem nenhum, o shortcode lista os próximos eventos, em cartões, do mais próximo ao mais distante.

| Atributo | Para que serve | Valores aceitos | Padrão |
|---|---|---|---|
| `layout` | Formato da listagem. | `cards` \| `table` | `cards` |
| `status` | Situação das inscrições. | `open` (abertas) \| `upcoming` (ainda não abriram) \| `ended` (encerradas) \| `all` (todas) | `all` |
| `mode` | Modalidade do evento. | `presencial` \| `virtual` \| `hibrido` \| vazio (todas) | vazio |
| `timeframe` | Recorte temporal pela **data do evento** (não pela inscrição). | `upcoming` (ainda vai acontecer) \| `past` (já aconteceu) \| `ongoing` (acontecendo hoje) \| `range` (intervalo definido por `date_from`/`date_to`) \| `all` | `upcoming` |
| `date_from` | Início do intervalo — só é usado com `timeframe="range"`. | `AAAA-MM-DD` | vazio |
| `date_to` | Fim do intervalo — só é usado com `timeframe="range"`. | `AAAA-MM-DD` | vazio |
| `limit` | Quantos eventos por página. `0` desliga a paginação e lista tudo numa página só. | número inteiro | `12` |
| `ids` | Restringe a estes eventos específicos, pelo ID, em vez de listar por filtro. | IDs separados por vírgula, ex.: `12,34,56` | vazio (todos) |
| `sort` | Coluna pela qual a lista começa ordenada (o visitante ainda pode trocar, na tabela). | `date` \| `deadline` \| `title` \| `location` \| `mode` | `date` |
| `order` | Sentido da ordenação inicial. | `asc` \| `desc` | `asc` |

{: .tip }
> **`status` filtra pela inscrição, `timeframe` filtra pela data do evento** — são coisas diferentes e combinam. Um evento pode ter a **data** no futuro (`timeframe=upcoming`) e a **inscrição** já encerrada (`status=ended`), por exemplo, se o prazo de inscrição for antes da data do evento.

{: .note }
> O ID de cada evento aparece na coluna **ID** da lista de eventos do painel (**V3REvent → Eventos**).

## Receitas prontas

Copie e ajuste. Todas assumem que você já colou o shortcode numa página publicada.

**Só os eventos com inscrição aberta, em tabela:**
```
[v3revent_events layout="table" status="open"]
```

**Os eventos deste semestre** (ajuste as datas para o período que quiser):
```
[v3revent_events timeframe="range" date_from="2026-07-01" date_to="2026-12-31"]
```

**Estes três eventos específicos**, na ordem em que você quiser apresentá-los:
```
[v3revent_events ids="12,34,56" limit="0"]
```

{: .tip }
> Sem `limit="0"` aqui, a listagem por `ids` ainda pagina normalmente — se você listou poucos eventos, geralmente não faz diferença, mas vale a pena desligar a paginação quando o objetivo é mostrar um conjunto fechado numa página só.

**Todos os eventos passados, do mais recente para o mais antigo:**
```
[v3revent_events timeframe="past" sort="date" order="desc"]
```

**Agenda de eventos virtuais, em cartões, sem limite de quantidade:**
```
[v3revent_events mode="virtual" limit="0"]
```

## Dicas e armadilhas

- **O padrão é "só o que vem por aí".** Sem o atributo `timeframe`, o shortcode mostra `upcoming` — eventos já encerrados **não aparecem** por padrão. Se a página é para servir de "histórico" ou "edições anteriores", troque para `timeframe="past"` ou `timeframe="all"`; senão a página vai parecer vazia assim que o último evento futuro passar.
- **Evento sem data cadastrada some da maioria dos recortes.** `timeframe=past`, `ongoing` e `range` dependem da data do evento para decidir se ele entra; sem data, só aparece em `upcoming` ou `all`. Se um evento sumiu da sua listagem, confira se a data foi preenchida no editor.
- **`ids` ignora os filtros de situação, modalidade e período.** Ele restringe **quais** eventos entram na consulta; `status`, `mode` e `timeframe` continuam sendo aplicados depois, sobre esse conjunto. Combinar `ids` com um filtro que nenhum deles atende resulta em lista vazia — na dúvida, use `status="all"` `timeframe="all"` junto com `ids`.
- **A listagem nunca traz rascunho**, para nenhum visitante — nem para quem está logado como administrador. Só eventos **publicados** aparecem.
- **`limit` alto ou `limit="0"` custa mais para carregar** em sites com muitos eventos publicados. Use `limit="0"` quando o objetivo justificar (ex.: `ids` com poucos eventos, ou paginação incomodando numa lista pequena) — não como padrão geral.

## Quando dá errado

| O que aparece | O que significa | O que fazer |
|---|---|---|
| "Nenhum evento encontrado." | Os filtros combinados não bateram com nenhum evento publicado (ex.: `status="open"` numa época sem inscrição aberta). | Revise os atributos — comece afrouxando `status` ou `timeframe` para `all` e vá restringindo de novo. |
| Um evento que você esperava ver não aparece | Ou ele não está **publicado**, ou a data/modalidade dele não bate com o filtro do shortcode. | Confira o status do evento no painel e, se usar `timeframe="range"`/`date_from`/`date_to`, confirme se a data do evento cai dentro do intervalo. |
| `date_from`/`date_to` parecem ignorados | Eles só valem com `timeframe="range"` — com qualquer outro valor (inclusive o padrão `upcoming`), são ignorados. | Adicione `timeframe="range"` junto dos dois atributos de data. |

{: .note }
> A listagem reaproveita a mesma regra de situação da inscrição usada na própria página do evento — não é um cálculo à parte, é o mesmo estado.

## Ver também

- **[Shortcodes e API](/modulos/shortcodes-e-api/)** — visão geral de todos os shortcodes do plugin.
- **[Gestão pelo site](/modulos/gestao-pelo-site/)** — o outro shortcode que foge do padrão de "um evento por vez": `[v3revent_gestao]` monta a gestão inteira numa página.
- **[Página do evento](/modulos/pagina-do-evento/)** — o destino de cada link "Ver evento" desta listagem.
