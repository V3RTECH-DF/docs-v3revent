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
| `[v3revent_events]` | Uma **listagem com vários eventos** (cartões ou tabela) — a vitrine pública dos seus eventos, já que o produto no WooCommerce é oculto de propósito. Veja a seção detalhada abaixo. | Numa página "Nossos Eventos": `[v3revent_events]` |

{: .note }
> Diferente dos demais, o `[v3revent_events]` **não usa `id`** (ele lista vários eventos, não um só). Para restringir a eventos específicos, use o parâmetro `ids` — veja a seção **[Página de listagem de eventos](#página-de-listagem-de-eventos-v3revent_events)** abaixo.

{: .note }
> A lista na tela é a **fonte viva** — ela reflete exatamente os shortcodes que o plugin oferece na sua versão. Se um shortcode novo for adicionado, ele aparece ali automaticamente, com o botão Copiar. O `[v3revent_registration]` também aceita `event_id` no lugar de `id` (compatibilidade), mas o padrão é **`id`**.

{: .tip }
> Você **não precisa** montar tudo com shortcodes. O V3REvent já gera uma **[página do evento](/modulos/pagina-do-evento/)** temática e completa. Os shortcodes servem para quando você quer encaixar **um pedaço** do evento numa página que você mesmo montou (ex.: só o formulário, ou só a programação).

## Página de listagem de eventos (v3revent_events)

### Por que meus eventos não aparecem na loja?

O V3REvent cria, para cada evento, um **produto no WooCommerce** — mas esse produto é **oculto do catálogo de propósito**. Ele existe só para levar o **preço** ao carrinho e ao checkout; quem tem a descrição, a programação, a identidade visual e o **formulário de inscrição** é a **[página do evento](/modulos/pagina-do-evento/)**, não o produto.

Por isso, navegando pela **loja** do seu site, você **não vai encontrar** os eventos — e isso é o comportamento esperado, não um bug.

{: .important }
> **Não torne o produto do evento visível na loja.** Se você mudar a visibilidade do produto no WooCommerce para "aparecer no catálogo", o que o visitante vê é a **página crua do WooCommerce** — sem descrição, sem programação e **sem o formulário de inscrição**. O jeito certo de ter uma vitrine com todos os seus eventos é criar uma página com o shortcode **`[v3revent_events]`**, descrito abaixo.

### Criando a página de eventos

1. No WordPress, vá em **Páginas → Adicionar nova** (ou edite uma página existente, como a home).
2. Dê um título à página, por exemplo **"Nossos Eventos"**.
3. Adicione um bloco **Shortcode** (Gutenberg) e cole `[v3revent_events]` — sem nenhum parâmetro, ele já lista os **próximos eventos publicados**, em cartões.
4. Publique a página e, se quiser, adicione-a ao **menu** do site, para o visitante chegar até ela navegando normalmente.

![Página com o shortcode [v3revent_events] listando eventos em cartões](/assets/screenshots/shortcode-eventos-cartoes.png)
<!-- CAPTURA PENDENTE: página pública com [v3revent_events] no layout padrão (cartões), mostrando 3+ eventos publicados com imagem, título, data/local, selo de situação da inscrição. -->

### Cartões ou tabela

O parâmetro **`layout`** decide a apresentação:

- **`cards`** (padrão) — cada evento vira um **cartão** com imagem, título, data, local, modalidade e o selo de situação da inscrição (Abertas / Em breve / Encerradas). Bom para uma vitrine visual.
- **`table`** — uma **tabela** com Evento, Data, Local, Modalidade e Prazo de inscrição. Os **cabeçalhos das colunas são clicáveis**: clique em "Data", por exemplo, para ordenar por data — clique de novo para inverter o sentido. Funciona **sem precisar de JavaScript** (é navegação normal por link), então funciona em qualquer site. Boa opção para listas longas ou históricos de edições passadas.

![Página com o shortcode [v3revent_events layout="table"] listando eventos em tabela ordenável](/assets/screenshots/shortcode-eventos-tabela.png)
<!-- CAPTURA PENDENTE: página pública com [v3revent_events layout="table"], mostrando a tabela com cabeçalhos clicáveis e a seta de ordenação ativa numa coluna. -->

### Todos os parâmetros

Todos são **opcionais** — usados sozinhos ou combinados. Cole o shortcode com os parâmetros entre aspas, por exemplo `[v3revent_events status="open" mode="virtual"]`.

| Parâmetro | O que faz | Valores aceitos | Padrão |
|---|---|---|---|
| `layout` | Apresentação da lista. | `cards` \| `table` | `cards` |
| `status` | Filtra pela **situação das inscrições** do evento. | `open` (abertas) \| `upcoming` (em breve) \| `ended` (encerradas) \| `all` (todas) | `all` |
| `mode` | Filtra pela **modalidade** do evento. | `presencial` \| `virtual` \| `hibrido` \| vazio (todas) | vazio (todas) |
| `timeframe` | Recorte pela **data do evento**. | `upcoming` (ainda vai acontecer) \| `past` (já aconteceu) \| `ongoing` (acontecendo hoje) \| `range` (intervalo — use com `date_from`/`date_to`) \| `all` (sem recorte) | `upcoming` |
| `date_from` | Início do intervalo (só com `timeframe="range"`). | Data no formato `AAAA-MM-DD` | vazio |
| `date_to` | Fim do intervalo (só com `timeframe="range"`). | Data no formato `AAAA-MM-DD` | vazio |
| `limit` | Quantos eventos por página. `0` = sem paginação, lista tudo numa página só. | Número inteiro | `12` |
| `ids` | Restringe a lista a estes eventos específicos, pelo **ID** (separados por vírgula). | Ex.: `12,34,56` | vazio (todos) |
| `sort` | Coluna usada para ordenar por padrão (o visitante pode trocar clicando no cabeçalho, no layout tabela). | `date` \| `deadline` \| `title` \| `location` \| `mode` | `date` |
| `order` | Sentido da ordenação padrão. | `asc` (crescente) \| `desc` (decrescente) | `asc` |

{: .note }
> O **ID do evento** aparece na coluna **ID** da tela **[Eventos](/modulos/eventos/)**.

### Exemplos prontos para copiar

**Só os próximos eventos com inscrições abertas:**
```
[v3revent_events status="open" timeframe="upcoming"]
```

**Todos os eventos passados, em tabela ordenada pela data mais recente primeiro:**
```
[v3revent_events layout="table" timeframe="past" sort="date" order="desc"]
```

**Só os eventos virtuais:**
```
[v3revent_events mode="virtual"]
```

**Um recorte de datas específico (ex.: eventos de agosto), em tabela:**
```
[v3revent_events layout="table" timeframe="range" date_from="2026-08-01" date_to="2026-08-31"]
```

**Uma vitrine com no máximo 6 eventos, sem paginação:**
```
[v3revent_events limit="6"]
```

{: .tip }
> **Prefere consultar direto do painel?** A aba **Shortcodes** desta tela mostra, para o `[v3revent_events]`, a **lista completa dos parâmetros** (com valores aceitos e padrão) e um **exemplo pronto** com o botão **Copiar** — sem precisar voltar a este manual.

## Dúvidas frequentes (integração)

**Qual das quatro abas eu uso?**
Para exibir conteúdo em páginas do site → **Shortcodes**. Para deixar outro sistema **ler** dados → **Chaves de API** + **[Referência da API](/modulos/api-referencia/)**. Para outro sistema **ser avisado** na hora → **[Webhooks](/modulos/api-webhooks/)**.

**Preciso saber programar?**
Para colar shortcodes, não. Para a API e os webhooks, você (ou quem cuida da sua automação) monta o fluxo no n8n praticamente sem código — veja as **[receitas](/modulos/api-receitas-n8n/)**.

**Isso tem custo extra?**
Não pelo V3REvent. A API e os webhooks fazem parte do plugin. O n8n (ou o serviço que você conectar) tem os próprios planos.

**É seguro?**
Sim, dentro dos cuidados de sempre: a API exige uma **chave** (revogável) e os webhooks são **assinados** e só entregam por **HTTPS**. Como o endpoint de inscritos traz dados pessoais, trate a chave como uma senha — veja a nota de LGPD em **[Chaves de API](/modulos/api-chaves/)**.
