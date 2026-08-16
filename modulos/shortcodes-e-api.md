---
title: Shortcodes e API
parent: Módulos
nav_order: 12
has_children: true
---

# Shortcodes e API

A tela **Shortcodes e API** (menu do V3REvent) reúne, num só lugar, tudo o que você precisa para **exibir conteúdo do evento em páginas** e **conectar o V3REvent a outros sistemas** — CRM, planilhas, dashboards e, principalmente, automações no [n8n](https://n8n.io). A tela tem **quatro abas**: Shortcodes, Chaves de API, API (referência) e Webhooks.

Esta página cobre a **visão geral** e os **shortcodes**. As demais abas têm páginas próprias, mais detalhadas:

- **[Chaves de API](/modulos/api-chaves/)** — como criar, dar escopo e revogar as chaves de acesso.
- **[Referência da API](/modulos/api-referencia/)** — todos os endpoints, com exemplos de requisição e resposta.
- **[Webhooks](/modulos/api-webhooks/)** — o V3REvent avisando outros sistemas em tempo real.
- **[Receitas de integração (n8n)](/modulos/api-receitas-n8n/)** — passo a passo de automações prontas.

## API ou webhook? A diferença que muda tudo

São dois caminhos opostos de integração. Escolher o certo economiza muito trabalho.

| | **API (leitura)** | **Webhooks** |
|---|---|---|
| **Sentido** | O sistema externo **puxa** (pergunta) os dados do V3REvent. | O V3REvent **empurra** (avisa) o sistema externo. |
| **Quando roda** | Quando você quiser — sob demanda ou em horários agendados. | Na hora exata em que algo acontece (uma inscrição confirmada, um check-in). |
| **Analogia** | Você liga perguntando "quantos inscritos temos?". | Eles te ligam assim que entra um inscrito novo. |
| **Bom para** | Sincronizar uma planilha/CRM periodicamente, alimentar um dashboard, conferir totais. | Disparar automações imediatas: mandar mensagem, criar contato, registrar linha assim que o fato ocorre. |

{: .tip }
> Na prática você costuma usar **os dois juntos**: o webhook dispara a automação no instante do evento (ex.: "inscrição confirmada → cria contato no CRM") e a API serve para uma **conferência periódica** ou para puxar um recorte grande (ex.: "toda noite, baixar a lista de presentes do evento").

### Casos de uso reais

- **Sincronizar um CRM ou mailing:** a cada inscrição confirmada, criar/atualizar o contato com nome, e-mail e evento (webhook → CRM).
- **Planilha viva de inscritos:** adicionar uma linha no Google Sheets a cada inscrição (webhook), ou reconstruir a planilha inteira de tempos em tempos (API).
- **Dashboard externo:** um painel em Power BI/Looker/Metabase que lê os **totais do evento** (`/stats`) e a **avaliação agregada** (`/evaluation`) pela API.
- **Automação de check-in:** ao registrar um check-in, mandar um WhatsApp de boas-vindas ou avisar um canal do time (webhook `attendee.checked_in`).

## Shortcodes

A aba **Shortcodes** lista todos os shortcodes do plugin, cada um com um botão **Copiar**. Um shortcode é um código curto entre colchetes que você **cola numa página ou post** para exibir ali um pedaço do evento — o formulário de inscrição, a programação, a galeria, os documentos, os patrocinadores ou os botões de compartilhamento.

![Aba Shortcodes](/assets/screenshots/api-shortcodes.png)

### Onde colar

No editor do WordPress (Gutenberg), adicione um bloco **Shortcode** e cole o código. Em editores clássicos ou construtores de página (Elementor, etc.), use o widget/bloco equivalente de "shortcode". O conteúdo aparece já com a **logo e as cores do evento**.

### Todos os shortcodes

Todos aceitam o atributo **`id`** — o **número do evento** (ex.: `[v3revent_gallery id="1257"]`). Você encontra o ID na **lista de eventos** (coluna **ID**), que ainda traz um botão para **copiar o shortcode de inscrição pronto**. Se o shortcode estiver na **própria página do evento**, pode **omitir** o `id` — ele já pega o evento da página.

| Shortcode | O que exibe | Exemplo de uso |
|---|---|---|
| `[v3revent_registration]` | O **formulário de inscrição** completo do evento (com preço ao vivo e checkout). | Numa página "Inscreva-se": `[v3revent_registration id="1257"]` |
| `[v3revent_schedule]` | A **programação** do evento (dias, horários, atividades). | Numa página "Programação": `[v3revent_schedule id="1257"]` |
| `[v3revent_gallery]` | A **galeria de imagens** do evento. | Numa página de edições anteriores: `[v3revent_gallery id="1257"]` |
| `[v3revent_documents]` | Os **documentos** do evento (regulamento, kit do participante…) como links de download. | Numa seção "Baixe o regulamento": `[v3revent_documents id="1257"]` |
| `[v3revent_sponsors]` | Os **patrocinadores**, agrupados por tipo (ouro, prata…). | No rodapé da página do evento: `[v3revent_sponsors]` |
| `[v3revent_share]` | Os **botões de compartilhamento** do evento nas redes. | Ao fim da página do evento: `[v3revent_share]` |

{: .note }
> A lista na tela é a **fonte viva** — ela reflete exatamente os shortcodes que o plugin oferece na sua versão. Se um shortcode novo for adicionado, ele aparece ali automaticamente, com o botão Copiar. O `[v3revent_registration]` também aceita `event_id` no lugar de `id` (compatibilidade), mas o padrão é **`id`**.

{: .tip }
> Você **não precisa** montar tudo com shortcodes. O V3REvent já gera uma **[página do evento](/modulos/pagina-do-evento/)** temática e completa. Os shortcodes servem para quando você quer encaixar **um pedaço** do evento numa página que você mesmo montou (ex.: só o formulário, ou só a programação).

## Dúvidas frequentes (integração)

**Qual das quatro abas eu uso?**
Para exibir conteúdo em páginas do site → **Shortcodes**. Para deixar outro sistema **ler** dados → **Chaves de API** + **[Referência da API](/modulos/api-referencia/)**. Para outro sistema **ser avisado** na hora → **[Webhooks](/modulos/api-webhooks/)**.

**Preciso saber programar?**
Para colar shortcodes, não. Para a API e os webhooks, você (ou quem cuida da sua automação) monta o fluxo no n8n praticamente sem código — veja as **[receitas](/modulos/api-receitas-n8n/)**.

**Isso tem custo extra?**
Não pelo V3REvent. A API e os webhooks fazem parte do plugin. O n8n (ou o serviço que você conectar) tem os próprios planos.

**É seguro?**
Sim, dentro dos cuidados de sempre: a API exige uma **chave** (revogável) e os webhooks são **assinados** e só entregam por **HTTPS**. Como o endpoint de inscritos traz dados pessoais, trate a chave como uma senha — veja a nota de LGPD em **[Chaves de API](/modulos/api-chaves/)**.
