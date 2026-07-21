---
title: Webhooks
parent: Shortcodes e API
grand_parent: Módulos
nav_order: 3
---

# Webhooks

Enquanto a [API](/modulos/api-referencia/) é o sistema externo **puxando** dados, os **webhooks** são o V3REvent **empurrando** o aviso assim que algo acontece. É o caminho ideal para automações imediatas no [n8n](https://n8n.io): a cada inscrição confirmada, check-in ou credencial emitida, o V3REvent faz um `POST` para a URL que você indicar, com os dados do que ocorreu.

![Aba Webhooks — novo webhook](/assets/screenshots/api-webhooks.png)

## Criar um webhook

1. Na aba **Webhooks**, clique em **Novo webhook**.
2. Informe a **URL de destino** — precisa ser **`https://`** (endereço seguro). É a URL que o sistema receptor te dá; no n8n, é a URL do nó **Webhook**.
3. Marque os **gatilhos** que quer receber (a lista completa está abaixo).
4. Defina o **escopo** — todos os eventos ou apenas eventos selecionados.
5. Salve. O webhook nasce com um **segredo** (secret) próprio, usado para assinar as entregas.

{: .important }
> **Só HTTPS**
>
> A URL de destino **precisa** começar com `https://`. Como o payload pode carregar dados pessoais (nome, e-mail, CPF de inscritos), o V3REvent recusa endereços `http://` para garantir que a informação trafegue criptografada. A assinatura (abaixo) garante **autenticidade**, não sigilo — por isso o HTTPS é obrigatório.

## Ativar, testar e acompanhar

- **Ativar/desativar:** um interruptor liga e desliga o webhook sem precisar apagá-lo. Desativado, ele para de enviar.
- **Testar:** o botão **Testar** envia na hora um payload de exemplo com `trigger = ping` para a URL. Serve para conferir, **antes de valer**, se o destino está recebendo e respondendo. Se o teste chega no n8n, a conexão está de pé.
- **Log de entregas:** o painel lista as **últimas entregas** (gatilho, horário, resultado — sucesso/falha). É onde você confere se os avisos estão saindo.
- **Remover:** você pode excluir um webhook quando quiser.

## Novas tentativas (retry)

Se o destino não responder com sucesso (qualquer resposta fora da faixa 2xx, ou um tempo de espera esgotado), o V3REvent **tenta de novo automaticamente**, com intervalos crescentes:

**1 minuto → 5 minutos → 30 minutos → 2 horas → 6 horas.**

São até **5 tentativas**. Se todas falharem, a entrega é marcada como **falha** no log. Cada tentativa aparece registrada. Isso significa que uma queda rápida do seu sistema receptor não faz você perder o aviso — ele reentrega quando o destino voltar.

## Os 9 gatilhos

Você escolhe, por webhook, quais destes disparam:

| Gatilho (chave) | Rótulo | Dispara quando |
|---|---|---|
| `event.created` | Evento criado | Um evento é criado. |
| `event.published` | Evento publicado | Um evento passa a publicado. |
| `event.cancelled` | Evento cancelado | Um evento publicado vai para a Lixeira. |
| `registration.opened` | Inscrições abertas | As inscrições do evento abrem (por botão ou por data). |
| `registration.closed` | Inscrições encerradas | As inscrições do evento fecham (por botão ou data-limite). |
| `registration.confirmed` | Inscrição confirmada | Um pedido é concluído e a inscrição é criada. |
| `registration.cancelled` | Inscrição cancelada | Um pedido é cancelado/reembolsado e a inscrição cai. |
| `attendee.checked_in` | Check-in realizado | Um inscrito faz check-in no evento. |
| `credential.issued` | Credencial emitida | A credencial (com QR) de um inscrito é emitida. |

{: .note }
> "Inscrições abertas/encerradas" por **data** são detectadas por uma verificação periódica — o aviso sai na virada detectada, não no segundo exato. Já quando você abre/fecha manualmente, o disparo é imediato.

## Formato do payload

Toda entrega é um `POST` com corpo em JSON no mesmo **envelope**:

```json
{
  "id": "3f9a...-uuid",
  "trigger": "registration.confirmed",
  "occurred_at": "2026-08-03T14:22:10+00:00",
  "event": {
    "id": 128,
    "title": "Congresso de Tecnologia 2026",
    "status": "publish",
    "date": "2026-09-12",
    "date_end": "2026-09-13",
    "location": "Centro de Convenções, Brasília-DF",
    "capacity": 500,
    "link": "https://seu-site.com.br/evento/congresso-de-tecnologia-2026/"
  },
  "data": { }
}
```

| Campo | Significado |
|---|---|
| `id` | Identificador único da entrega. |
| `trigger` | Qual gatilho disparou (ex.: `registration.confirmed`). |
| `occurred_at` | Quando o fato aconteceu. |
| `event` | O resumo do evento relacionado. |
| `data` | O conteúdo específico do gatilho (veja abaixo). |

### Exemplo: `registration.confirmed`

O `data` traz a **inscrição** e a **lista de inscritos**:

```json
{
  "id": "3f9a1b2c-uuid",
  "trigger": "registration.confirmed",
  "occurred_at": "2026-08-03T14:22:10+00:00",
  "event": { "id": 128, "title": "Congresso de Tecnologia 2026", "status": "publish", "date": "2026-09-12", "date_end": "2026-09-13", "location": "Centro de Convenções, Brasília-DF", "capacity": 500, "link": "https://seu-site.com.br/evento/congresso-de-tecnologia-2026/" },
  "data": {
    "registration": {
      "id": 542,
      "event_id": 128,
      "event_name": "Congresso de Tecnologia 2026",
      "responsible_name": "Maria Souza",
      "responsible_email": "maria@empresa.com.br",
      "total_attendees": 5,
      "unit_price": 200.00,
      "total_price": 1000.00,
      "status": "paid",
      "order_id": 8891,
      "created_at": "2026-08-03 14:22:10"
    },
    "attendees": [
      {
        "public_id": "ATT-7F3A9C",
        "field_data": { "nome_completo": "João Lima", "email": "joao@empresa.com.br", "cpf": "123.456.789-09" },
        "responsible_name": "Maria Souza",
        "responsible_email": "maria@empresa.com.br",
        "status": "paid",
        "order_id": 8891,
        "checked_in_at": null
      }
    ]
  }
}
```

### Exemplo: `attendee.checked_in`

O `data` traz o **inscrito** que fez check-in:

```json
{
  "id": "7c1d2e3f-uuid",
  "trigger": "attendee.checked_in",
  "occurred_at": "2026-09-12T09:14:02+00:00",
  "event": { "id": 128, "title": "Congresso de Tecnologia 2026", "status": "publish", "date": "2026-09-12", "date_end": "2026-09-13", "location": "Centro de Convenções, Brasília-DF", "capacity": 500, "link": "https://seu-site.com.br/evento/congresso-de-tecnologia-2026/" },
  "data": {
    "attendee": {
      "public_id": "ATT-7F3A9C",
      "field_data": { "nome_completo": "João Lima", "email": "joao@empresa.com.br", "cpf": "123.456.789-09" },
      "responsible_name": "Maria Souza",
      "responsible_email": "maria@empresa.com.br",
      "status": "paid",
      "order_id": 8891,
      "checked_in_at": "2026-09-12 09:14:02"
    }
  }
}
```

{: .note }
> Os gatilhos de inscrito — `attendee.checked_in` e `credential.issued` — trazem o inscrito em `data.attendee`. Os de inscrição — `registration.confirmed` e `registration.cancelled` — trazem `data.registration` + `data.attendees`. Nos gatilhos de ciclo de vida do evento e de abertura/encerramento de inscrições, a informação essencial vem no `event` do envelope.

## Cabeçalhos enviados

Cada `POST` vai com estes cabeçalhos:

| Cabeçalho | Conteúdo |
|---|---|
| `Content-Type` | `application/json` |
| `X-V3REvent-Event` | A chave do gatilho (ex.: `registration.confirmed`). |
| `X-V3REvent-Signature` | A assinatura: `sha256=<HMAC-SHA256 do corpo com o segredo>`. |
| `X-V3REvent-Delivery` | O identificador único da entrega (o mesmo `id` do envelope). |

## Validar a assinatura (é mesmo do V3REvent?)

Para ter certeza de que a chamada veio do seu V3REvent — e não de alguém se passando por ele — valide a **assinatura HMAC**:

1. Pegue o **corpo cru** da requisição (o texto JSON exatamente como chegou, sem re-serializar).
2. Calcule o **HMAC-SHA256** desse corpo usando o **segredo do webhook** (aquele gerado na criação).
3. Monte `sha256=<resultado em hexadecimal>` e compare com o cabeçalho `X-V3REvent-Signature`. Se baterem, a chamada é autêntica.

### Como fazer no n8n

No fluxo que recebe o webhook, adicione um nó **Crypto** (ou um nó **Code**) logo após o nó Webhook:

- **Operação:** HMAC, algoritmo **SHA256**.
- **Valor de entrada:** o **corpo bruto** recebido (`body`).
- **Segredo (secret key):** o segredo do webhook do V3REvent.
- **Saída:** em **hexadecimal**.

Depois, compare `sha256=` + esse valor com o cabeçalho `X-V3REvent-Signature` (num nó **IF**). Só siga o fluxo se forem iguais — assim você descarta chamadas forjadas.

{: .tip }
> Guarde o **segredo do webhook** no n8n como uma credencial/variável, não solto no fluxo. E lembre: a assinatura confirma **quem enviou**; o HTTPS é o que mantém o conteúdo **em sigilo** no caminho.
