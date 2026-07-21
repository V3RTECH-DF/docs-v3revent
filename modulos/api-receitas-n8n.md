---
title: Receitas de integração (n8n)
parent: Shortcodes e API
grand_parent: Módulos
nav_order: 4
---

# Receitas de integração (n8n)

Duas automações prontas para copiar, uma de cada tipo: uma via **webhook** (o V3REvent avisa o n8n) e outra via **API** (o n8n pergunta ao V3REvent). O [n8n](https://n8n.io) é uma ferramenta de automação em que você monta fluxos ligando "nós" — quase sem programar.

> Antes de começar, tenha em mãos:
> - a **URL base** da API (aba **API (referência)** do plugin);
> - uma **[chave de API](/modulos/api-chaves/)** (para as receitas via API);
> - acesso ao seu n8n para criar fluxos.

## Receita 1 — A cada inscrição confirmada, registrar em planilha/CRM (webhook)

**Objetivo:** toda vez que alguém conclui uma inscrição paga, adicionar uma linha no Google Sheets (ou criar/atualizar um contato no CRM), sem ninguém mexer.

**No n8n:**

1. Crie um fluxo novo e adicione um nó **Webhook** (método **POST**). Ative o fluxo (ou use a URL de produção) e **copie a URL** que o n8n gera. Ela precisa ser **`https://`**.
2. *(Recomendado)* Adicione um nó **Crypto/Code** para validar a assinatura — veja **[como validar no n8n](/modulos/api-webhooks/#como-fazer-no-n8n)**.
3. Adicione o nó de destino:
   - **Google Sheets → Append Row**, mapeando os campos do payload: `data.registration.responsible_name`, `data.registration.responsible_email`, `data.registration.total_attendees`, `event.title`; ou
   - **HubSpot / RD Station / seu CRM → Create/Update Contact**, mapeando nome e e-mail do responsável (ou percorrendo `data.attendees` para criar um contato por inscrito).

**No V3REvent:**

4. Vá em **[Webhooks](/modulos/api-webhooks/)** → **Novo webhook**.
5. Cole a **URL do nó Webhook do n8n** no campo **URL de destino**.
6. Marque o gatilho **Inscrição confirmada** (`registration.confirmed`) e escolha o escopo (o evento ou todos).
7. Salve e clique em **Testar** — confira no n8n que o payload de teste (`trigger: ping`) chegou.

Pronto. A cada nova inscrição paga, o n8n recebe os dados e faz o resto.

{: .tip }
> Quer uma linha **por participante** em vez de por inscrição? No n8n, adicione um nó que percorra `data.attendees` (ex.: um **Split Out**/**Item Lists**) antes do Google Sheets, e use os campos de cada inscrito (`field_data`, `public_id`).

## Receita 2 — Puxar periodicamente os presentes de um evento (API)

**Objetivo:** de tempos em tempos (ex.: toda noite do evento), baixar a lista de **quem já fez check-in** e enviar a um relatório, planilha ou canal do time.

**No n8n:**

1. Crie um fluxo com um nó **Schedule Trigger** (ex.: a cada 1 hora, ou uma vez por dia).
2. Adicione um nó **HTTP Request**:
   - **Método:** GET.
   - **URL:** `https://SEU-SITE.com.br/wp-json/v3revent/v1/public/attendees?event_id=128&present=1`
     (troque `128` pelo id do seu evento; `present=1` traz só os presentes).
   - **Cabeçalho (Header):** nome `X-V3REvent-Api-Key`, valor `v3re_...` (sua chave). No n8n, o ideal é guardar isso como uma credencial "Header Auth".
3. Adicione o destino: **Google Sheets** para reconstruir a planilha, um **e-mail** com o total, ou uma mensagem num canal (Slack/Teams/WhatsApp) com quantos presentes há.

{: .note }
> A resposta é uma **lista** de inscritos (com PII). Se o evento tiver muitos presentes, use **[paginação](/modulos/api-referencia/#paginação)** (`page` e `per_page`) — vá aumentando o `page` até vir uma página com menos itens que o `per_page`.

{: .tip }
> **Onde vai cada credencial:** a **chave de API** entra no cabeçalho do nó **HTTP Request** (Receita 2). A **URL do webhook do n8n** entra no campo "URL de destino" ao criar o webhook no V3REvent (Receita 1), e o **segredo do webhook** entra no nó de validação da assinatura, no lado do n8n.

## Ideias para adaptar

- **Boas-vindas no check-in:** gatilho `attendee.checked_in` → mensagem de boas-vindas ou aviso ao time (`data.attendee`).
- **Painel de vendas:** `Schedule` → `GET /events/{id}/stats` → atualizar um dashboard com inscritos e arrecadação.
- **Alerta de novo evento:** gatilho `event.published` → postar num canal "acabou de entrar no ar o evento X".
- **Pesquisa de satisfação consolidada:** `Schedule` → `GET /events/{id}/evaluation` → montar um resumo da nota média do evento.
