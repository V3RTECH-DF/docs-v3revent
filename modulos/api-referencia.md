---
title: Referência da API
parent: Shortcodes e API
grand_parent: Módulos
nav_order: 2
---

# Referência da API

A API pública do V3REvent é **somente leitura**: ela deixa um sistema externo **consultar** eventos, inscrições, inscritos, totais e avaliação. Não há criação, edição ou exclusão de dados pela API.

A aba **API (referência)** no plugin mostra a URL base, o cabeçalho de autenticação e a lista de endpoints com um exemplo pronto — é a **documentação viva**, sempre igual ao que a sua versão do plugin oferece. Esta página traz os mesmos endpoints com exemplos completos de requisição e resposta.

![Aba API (referência)](/assets/screenshots/api-referencia.png)

## URL base

Todos os endpoints ficam sob:

```
https://SEU-SITE.com.br/wp-json/v3revent/v1/public
```

Troque `SEU-SITE.com.br` pelo domínio do seu WordPress. A tela **API (referência)** mostra a URL base exata do seu site — copie de lá para não errar.

## Autenticação

Toda requisição precisa do cabeçalho com a sua **[chave de API](/modulos/api-chaves/)**:

```
X-V3REvent-Api-Key: v3re_a1b2c3d4e5f6...
```

Sem esse cabeçalho, ou com uma chave inválida/revogada, a resposta é `401`. Se a chave for restrita a certos eventos e você pedir um evento fora do escopo, a resposta é `403`.

## Paginação

As listas (`/events`, `/registrations`, `/attendees`) aceitam dois parâmetros na URL:

| Parâmetro | O que faz | Padrão |
|---|---|---|
| `page` | Número da página (começa em 1). | `1` |
| `per_page` | Quantos itens por página. | `20` (máximo `100`) |

Cada página devolve uma **lista** (array) de itens. Para percorrer tudo, vá aumentando o `page` (`1`, `2`, `3`…) até uma página vir com **menos itens que o `per_page`** — sinal de que chegou ao fim.

```bash
# Segunda página, 50 eventos por página
curl "https://SEU-SITE.com.br/wp-json/v3revent/v1/public/events?page=2&per_page=50" \
  -H "X-V3REvent-Api-Key: v3re_a1b2c3d4e5f6..."
```

## Endpoints

Sete endpoints, todos `GET`.

### 1. Listar eventos

`GET /events`

Lista os eventos (dentro do escopo da chave).

**Filtros:** `status`, `search`, `page`, `per_page`.

```bash
curl "https://SEU-SITE.com.br/wp-json/v3revent/v1/public/events?search=congresso" \
  -H "X-V3REvent-Api-Key: v3re_a1b2c3d4e5f6..."
```

```json
[
  {
    "id": 128,
    "title": "Congresso de Tecnologia 2026",
    "status": "publish",
    "date": "2026-09-12",
    "date_end": "2026-09-13",
    "location": "Centro de Convenções, Brasília-DF",
    "capacity": 500,
    "link": "https://seu-site.com.br/evento/congresso-de-tecnologia-2026/"
  }
]
```

### 2. Detalhe do evento

`GET /events/{id}`

Retorna o evento completo: descrição (`content`), programação, faixas de preço, **patrocinadores públicos** (nome, logo e tipo) e **documentos públicos** (título e URL de download).

```bash
curl "https://SEU-SITE.com.br/wp-json/v3revent/v1/public/events/128" \
  -H "X-V3REvent-Api-Key: v3re_a1b2c3d4e5f6..."
```

```json
{
  "id": 128,
  "title": "Congresso de Tecnologia 2026",
  "status": "publish",
  "date": "2026-09-12",
  "date_end": "2026-09-13",
  "location": "Centro de Convenções, Brasília-DF",
  "capacity": 500,
  "link": "https://seu-site.com.br/evento/congresso-de-tecnologia-2026/",
  "content": "<p>Dois dias de palestras e workshops sobre tecnologia.</p>",
  "schedule": [
    { "time": "09:00", "title": "Abertura", "day": "2026-09-12" }
  ],
  "pricing": [
    { "min": 1, "max": 4, "price": 250.00 },
    { "min": 5, "max": 10, "price": 200.00 }
  ],
  "sponsors": [
    { "name": "Empresa Ouro Ltda", "logo_url": "https://seu-site.com.br/wp-content/uploads/ouro.png", "type": "ouro" }
  ],
  "documents": [
    { "title": "Regulamento", "url": "https://seu-site.com.br/wp-content/uploads/regulamento.pdf" }
  ]
}
```

{: .note }
> Os campos de `schedule` e `pricing` refletem como você preencheu o evento no editor, então o conteúdo exato de cada item pode variar. Os **patrocinadores** trazem só o que é público (nome, logo, tipo) — o valor financeiro do patrocínio é interno e **não** aparece na API.

### 3. Totais do evento

`GET /events/{id}/stats`

Os números-resumo do evento.

```bash
curl "https://SEU-SITE.com.br/wp-json/v3revent/v1/public/events/128/stats" \
  -H "X-V3REvent-Api-Key: v3re_a1b2c3d4e5f6..."
```

```json
{
  "total_registrations": 87,
  "total_attendees": 214,
  "paid_attendees": 198,
  "pending_attendees": 16,
  "checked_in": 173,
  "total_revenue": 48600.00
}
```

| Campo | Significado |
|---|---|
| `total_registrations` | Nº de inscrições (pedidos) do evento. |
| `total_attendees` | Nº total de inscritos (participantes). |
| `paid_attendees` | Inscritos com pagamento confirmado. |
| `pending_attendees` | Inscritos aguardando pagamento. |
| `checked_in` | Inscritos que fizeram check-in (presentes). |
| `total_revenue` | Valor arrecadado. |

### 4. Avaliação agregada

`GET /events/{id}/evaluation`

Os resultados da **avaliação do evento**, sempre **agregados e anônimos** (nunca resposta individual).

```bash
curl "https://SEU-SITE.com.br/wp-json/v3revent/v1/public/events/128/evaluation" \
  -H "X-V3REvent-Api-Key: v3re_a1b2c3d4e5f6..."
```

```json
{
  "results": [
    { "question": "Como você avalia o evento?", "average": 4.6, "responses": 120 }
  ],
  "present": 173,
  "responded": 120,
  "responses_total": 120
}
```

| Campo | Significado |
|---|---|
| `results` | A síntese por pergunta (médias/contagens, conforme o tipo da pergunta). |
| `present` | Quantos participantes estavam presentes (elegíveis a responder). |
| `responded` | Quantos presentes responderam à avaliação. |
| `responses_total` | Total de respostas recebidas. |

{: .note }
> O formato de cada item em `results` depende do tipo de pergunta (nota, múltipla escolha, texto). O exemplo acima é ilustrativo; consulte a resposta real do seu evento para o detalhe.

### 5. Listar inscrições

`GET /registrations`

Lista as inscrições (uma inscrição = um pedido, que pode conter vários inscritos).

**Filtros:** `event_id`, `status`, `from`, `to`, `page`, `per_page`. Os filtros `from` e `to` recortam pela **data da inscrição** (formato `AAAA-MM-DD`).

```bash
curl "https://SEU-SITE.com.br/wp-json/v3revent/v1/public/registrations?event_id=128&status=paid" \
  -H "X-V3REvent-Api-Key: v3re_a1b2c3d4e5f6..."
```

```json
[
  {
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
  }
]
```

### 6. Detalhe da inscrição

`GET /registrations/{id}`

A inscrição com a **lista dos seus inscritos** anexada em `attendees` (mesmo formato do endpoint de inscritos, abaixo).

```bash
curl "https://SEU-SITE.com.br/wp-json/v3revent/v1/public/registrations/542" \
  -H "X-V3REvent-Api-Key: v3re_a1b2c3d4e5f6..."
```

```json
{
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
  "created_at": "2026-08-03 14:22:10",
  "attendees": [
    {
      "public_id": "ATT-7F3A9C",
      "field_data": { "nome_completo": "João Lima", "email": "joao@empresa.com.br", "cpf": "123.456.789-09" },
      "responsible_name": "Maria Souza",
      "responsible_email": "maria@empresa.com.br",
      "status": "paid",
      "order_id": 8891,
      "checked_in_at": "2026-09-12 09:14:02"
    }
  ]
}
```

### 7. Listar inscritos

`GET /attendees`

Os **participantes** de um evento, com **paridade de export** — os mesmos dados da exportação XLSX/CSV, incluindo os campos do formulário e o CPF.

**Filtros:** `event_id` (**obrigatório**), `present`, `page`, `per_page`.

- `event_id` é obrigatório — sem ele, a resposta é `400`.
- `present=1` (ou `present=true`) traz **só quem fez check-in**.

```bash
# Só os presentes do evento 128
curl "https://SEU-SITE.com.br/wp-json/v3revent/v1/public/attendees?event_id=128&present=1" \
  -H "X-V3REvent-Api-Key: v3re_a1b2c3d4e5f6..."
```

```json
[
  {
    "public_id": "ATT-7F3A9C",
    "field_data": {
      "nome_completo": "João Lima",
      "email": "joao@empresa.com.br",
      "cpf": "123.456.789-09",
      "empresa": "Empresa Ltda"
    },
    "responsible_name": "Maria Souza",
    "responsible_email": "maria@empresa.com.br",
    "status": "paid",
    "order_id": 8891,
    "checked_in_at": "2026-09-12 09:14:02"
  }
]
```

| Campo do inscrito | Significado |
|---|---|
| `public_id` | Identificador público do inscrito (o mesmo que vai no QR da credencial). |
| `field_data` | Os campos do formulário preenchidos (nome, e-mail, CPF e o que mais você configurou). As chaves correspondem aos campos do seu formulário. |
| `responsible_name` / `responsible_email` | O responsável pela inscrição. Em eventos individuais, são os dados do próprio participante. |
| `status` | Situação do inscrito (ex.: `paid`, `pending`). |
| `order_id` | Nº do pedido no WooCommerce. |
| `checked_in_at` | Data/hora do check-in, ou `null` se ainda não fez. |

{: .important }
> Este endpoint devolve **dados pessoais completos** (PII). Use uma chave de **escopo restrito** ao evento e trate a resposta com o mesmo cuidado de uma planilha de participantes. Veja a nota de LGPD em **[Chaves de API](/modulos/api-chaves/)**.

## Códigos de erro

Quando algo dá errado, a API responde com um código HTTP e uma mensagem em JSON.

| Código | Quando acontece | O que fazer |
|---|---|---|
| **401** | Cabeçalho `X-V3REvent-Api-Key` ausente, ou chave inválida/revogada. | Confira o cabeçalho e se a chave ainda está ativa. Se foi revogada, gere outra. |
| **403** | A chave é válida, mas o evento pedido **está fora do escopo** dela. | Use uma chave com acesso àquele evento, ou amplie o escopo. |
| **400** | Falta um parâmetro obrigatório — no `/attendees`, o `event_id`. | Inclua o `event_id` na URL. |
| **404** | O evento/inscrição pedido **não existe**. | Confira o `id`. |

Exemplo de corpo de erro:

```json
{
  "code": "v3revent_api_unauthorized",
  "message": "Chave de API ausente ou inválida.",
  "data": { "status": 401 }
}
```
