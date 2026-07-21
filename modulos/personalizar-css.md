---
title: Personalizar com CSS
parent: Módulos
nav_order: 13
---

# Personalizar com CSS

As telas públicas do V3REvent — o **formulário de inscrição** e a **página do evento** — já saem estilizadas com a logo e as cores do seu evento. Mas, se você quer ir além (ajustar espaçamentos, fontes, cores de detalhe ou reaproveitar os elementos em conteúdos com design mais avançado), o plugin expõe um conjunto de **classes CSS** e de **variáveis de estilo** que você pode sobrescrever pelo seu tema, sem tocar no código do plugin.

Esta página é uma **referência técnica** para quem sabe (ou quer aprender) um pouco de CSS. Se você só precisa trocar a logo e as cores do evento, isso é feito no editor, sem CSS — veja **[Editor de evento](/modulos/editor-evento/)**.

---

## Onde escrever o seu CSS

O caminho recomendado é o **CSS adicional** do WordPress, que não é apagado quando o plugin ou o tema é atualizado:

1. No painel do WordPress, abra **Aparência → Personalizar**.
2. Clique em **CSS adicional**.
3. Escreva as suas regras e clique em **Publicar**.

O CSS adicional é carregado **depois** dos estilos do plugin, então, com a mesma especificidade, as suas regras vencem — sem precisar recorrer a `!important` na maioria dos casos.

{: .important }
> **Duas telas públicas ficam fora do alcance do CSS adicional.** A **página de avaliação pós-evento** e a **página web da credencial / painel de check-in** são geradas como documentos independentes, que **não usam o cabeçalho do seu tema**. Por isso, o CSS adicional do Personalizar **não chega** a elas. O que esta página descreve vale para o **formulário de inscrição** e a **página do evento**.

---

## Prefira variáveis a redefinir regras

O V3REvent controla cor, fonte, cantos e espaçamento por meio de **variáveis CSS** (as *custom properties*, que começam com `--v3revent-`). Sobrescrever uma variável é a forma mais segura e estável de personalizar: você muda um valor e ele se propaga por todos os componentes de uma vez, sem depender da estrutura interna do HTML.

Exemplo — deixar o formulário e a página com cantos mais arredondados, uma fonte diferente e um verde como cor de destaque:

```css
:root {
  --v3revent-secondary: #0f9d58;   /* cor de destaque / botão de compra / faixa ativa */
  --v3revent-font: Georgia, serif; /* fonte das telas públicas */
  --v3revent-radius: 14px;         /* cantos dos cards e campos */
}
```

{: .tip }
> As cores primária e secundária **por evento** você define no editor (aba **Aparência**), sem CSS. Use a sobrescrita de `--v3revent-primary` / `--v3revent-secondary` acima quando quiser um ajuste **global**, valendo para todos os eventos do site.

### Variáveis que você pode sobrescrever

Todas têm um valor padrão; várias são **derivadas** de outra (por exemplo, o hover do botão é calculado a partir da cor primária), então mudar a cor base já ajusta as derivadas.

| Variável | O que controla | Padrão |
|---|---|---|
| `--v3revent-primary` | Cor primária da marca (cabeçalhos, links, foco) | `#1e2d2b` |
| `--v3revent-secondary` | Cor de destaque: botão de compra, faixa de preço ativa, realces | `#c2272d` |
| `--v3revent-amber` | Cor complementar (âmbar), usada em alguns realces | `#da8c1c` |
| `--v3revent-primary-hover` | Hover do botão primário | derivada de `primary` |
| `--v3revent-accent-hover` | Hover do botão de compra | derivada de `secondary` |
| `--v3revent-focus-ring` | Anel de foco dos campos | derivada de `primary` |
| `--v3revent-success` / `--v3revent-warning` / `--v3revent-danger` / `--v3revent-info` | Cores dos avisos (sucesso, atenção, erro, informação) e da validação | `#10B981` / `#F59E0B` / `#EF4444` / `#3B82F6` |
| `--v3revent-bg` | Cor de fundo geral | `#f8fafc` |
| `--v3revent-card-bg` | Fundo dos cards (seções, resumo) | `#ffffff` |
| `--v3revent-field-bg` | Fundo dos campos do formulário e dos botões secundários | `#ffffff` (escuro: `#0f172a`) |
| `--v3revent-border` / `--v3revent-border-strong` | Cores das bordas | `#e2e8f0` / `#cbd5e1` |
| `--v3revent-text` | Cor do texto principal | `#1e293b` |
| `--v3revent-muted` | Cor do texto secundário (legendas, dicas) | `#64748b` |
| `--v3revent-accent-text` | Cor **primária** da marca quando usada como texto (garante contraste, inclusive no modo escuro) | igual a `primary` |
| `--v3revent-secondary-text` | Cor **secundária** (de destaque) quando usada como texto: preço da faixa, total do resumo, ícones da barra de info, hover de link. Clareada no modo escuro para não sumir | igual a `secondary` |
| `--v3revent-font` | Família tipográfica das telas públicas | `inherit` |
| `--v3revent-radius` / `--v3revent-radius-lg` | Arredondamento dos cantos (padrão / grande) | `8px` / `12px` |
| `--v3revent-shadow` | Sombra dos cards | sombra suave |
| `--v3revent-section-gap` / `--v3revent-section-pad` | Espaço **entre** e **dentro** das seções da página do evento | varia pelo tema |

{: .warning }
> **`--v3revent-accent-text` e `--v3revent-secondary-text` são sensíveis a contraste.** Elas existem justamente para o texto da marca (primária e secundária) continuar legível no **modo escuro** da página do evento, onde são clareadas automaticamente. Se você fixar um valor, teste nos dois modos (claro e escuro) para não deixar texto ilegível.

{: .note }
> A cor primária, a secundária e a fonte **do evento** são injetadas pelo plugin em `:root`. Como o CSS adicional carrega depois, a sua regra `:root { --v3revent-primary: … }` vence. Para um ajuste que valha **em um evento só**, mire uma classe daquela tela (ex.: dentro de `.v3revent-registration-wrap`) em vez da variável global.

---

## Classes por área

As tabelas abaixo listam as classes reais emitidas pelas telas públicas, para quando você precisa mirar **um elemento específico**. Todas começam com o prefixo `v3revent-`.

{: .warning }
> **Classes são um contrato de estilo, não de estrutura.** Os nomes servem para você aplicar aparência; a **estrutura interna do HTML pode mudar entre versões** do plugin. Use com parcimônia, prefira sobrescrever variáveis (acima) e evite depender do aninhamento exato dos elementos. Depois de uma atualização do plugin, confira se as suas personalizações continuam válidas.

### Formulário de inscrição

O container raiz é `.v3revent-registration-wrap` — use-o como âncora para restringir o seu CSS ao formulário.

| Classe | Para que serve |
|---|---|
| `.v3revent-registration-wrap` | Container raiz do formulário |
| `.v3revent-event-logo` | Bloco da logo do evento no topo |
| `.v3revent-event-info-bar` / `.v3revent-info-item` | Barra com data e local; cada item da barra |
| `.v3revent-reg-scope` | Bloco "Para quem é esta inscrição?" (individual × grupo) |
| `.v3revent-responsible-section` / `.v3revent-attendees-section` | Cards de seção: responsável / participantes |
| `.v3revent-form-grid` | Grade dos campos |
| `.v3revent-form-group` | Wrapper de um campo (variante `--full` ocupa a linha inteira) |
| `.v3revent-required` | Marcador `*` de campo obrigatório |
| `.v3revent-input` | Campos de texto, seleção e área de texto |
| `.v3revent-error` / `.v3revent-valid` | Estados de validação de um campo |
| `.v3revent-field-error` | Mensagem de erro abaixo do campo |
| `.v3revent-radio-group` / `.v3revent-checkbox-group` / `.v3revent-radio-label` | Grupos e opções de escolha por inscrito |
| `.v3revent-attendees-header` / `.v3revent-attendee-count` / `.v3revent-attendees-list` | Cabeçalho, contador e lista de participantes |
| `.v3revent-attendee-card` / `.v3revent-attendee-header` | Card de cada participante e seu cabeçalho |
| `.v3revent-summary` / `.v3revent-summary-grid` / `.v3revent-summary-row` / `.v3revent-summary-tier` / `.v3revent-summary-total` | Bloco de **resumo de preço ao vivo** |
| `.v3revent-consent-section` / `.v3revent-consent-label` / `.v3revent-consent-checkbox` / `.v3revent-consent-error` | Bloco de consentimento (LGPD) |
| `.v3revent-networking-checkbox` | Aceite de networking do inscrito |
| `.v3revent-actions` | Wrapper do botão final |
| `.v3revent-notices` / `.v3revent-notice` | Avisos gerais (variantes `--error`, `--success`, `--info`, `--warning`) |
| `.v3revent-thankyou-notice` | Mensagem de agradecimento pós-inscrição |
| `.v3revent-link` | Links (política de privacidade, baixar modelo…) |

**Importar participantes por planilha:** `.v3revent-import-section`, `.v3revent-import-area`, `.v3revent-import-hint`, `.v3revent-file-label`, `.v3revent-file-input`, `.v3revent-file-btn`, `.v3revent-file-name`, `.v3revent-import-status` (variantes `.success` / `.error`).

### Botões

Um único sistema, usado no formulário e nos elementos públicos:

| Classe | Para que serve |
|---|---|
| `.v3revent-btn` | Base de todos os botões |
| `.v3revent-btn--primary` | Botão primário (cor da marca) |
| `.v3revent-btn--cta` | Botão de compra / avançar para o checkout |
| `.v3revent-btn--secondary` | Botão secundário |
| `.v3revent-btn--add` / `.v3revent-btn--remove` | Adicionar / remover participante |
| `.v3revent-btn--lg` | Variante de largura total / grande |

### Tabela de preços e lotes

| Classe | Para que serve |
|---|---|
| `.v3revent-pricing-tiers` | Card com a tabela de faixas de preço (por quantidade) |
| `.v3revent-pricing-lots` | Variante para **lotes por data** (lista em coluna) |
| `.v3revent-tier-item` | Cada faixa ou lote; a variante `.active` realça o vigente |
| `.v3revent-tier-label` / `.v3revent-tier-price` | Rótulo e preço da faixa |
| `.v3revent-lot-name` / `.v3revent-lot-dates` / `.v3revent-lot-badge` | Nome, período e etiqueta de situação do lote |

### Página do evento (motor de páginas)

A página temática tem o container raiz `.v3revent-page`, com **modificadores** que refletem o layout e o tema escolhidos no editor (aba **Página**):

| Grupo | Classes |
|---|---|
| Largura | `.v3revent-page--boxed`, `.v3revent-page--full` |
| Modo de cor | `.v3revent-page--light`, `.v3revent-page--dark`, `.v3revent-page--system` |
| Fonte | `.v3revent-page--font-sans`, `.v3revent-page--font-serif`, `.v3revent-page--font-rounded` |
| Cantos | `.v3revent-page--shape-sharp`, `.v3revent-page--shape-soft`, `.v3revent-page--shape-round` |
| Densidade | `.v3revent-page--density-cozy`, `.v3revent-page--density-airy` |
| Decoração | `.v3revent-page--accent-bar`, `.v3revent-page--accent-blocks` |

Cada seção da página é `.v3revent-page-section`, com uma variante por tipo: `--registration`, `--info`, `--gallery`, `--schedule`, `--sponsors`, `--share`, `--hero`.

**Hero:** `.v3revent-page-hero` (variantes `--image`, `--image-text`, `--text`), com `.v3revent-page-hero-media`, `.v3revent-page-hero-img`, `.v3revent-page-hero-content`, `.v3revent-page-hero-title`, `.v3revent-page-hero-meta`, `.v3revent-page-hero-location`.

**Informações:** `.v3revent-page-info-meta`, `.v3revent-page-info-date`, `.v3revent-page-info-location`, `.v3revent-page-info-description`.

### Programação

`.v3revent-schedule` · `.v3revent-schedule-day-title` (variante `--undated`) · `.v3revent-schedule-sessions` · `.v3revent-schedule-session` · `.v3revent-schedule-session-inner` · `.v3revent-schedule-time` · `.v3revent-schedule-heading` · `.v3revent-schedule-title` · `.v3revent-schedule-track` · `.v3revent-schedule-meta` · `.v3revent-schedule-speakers` · `.v3revent-schedule-location` · `.v3revent-schedule-description`.

{: .note }
> A cor de cada **trilha** da programação é aplicada individualmente por sessão. Para mudar a cor de **todas** as trilhas de uma vez, mire a classe `.v3revent-schedule-track` diretamente (não há uma variável global para isso).

### Galeria

`.v3revent-gallery` (grade) · `.v3revent-gallery-item` (card) · `.v3revent-gallery-img` (imagem) · `.v3revent-gallery-caption` (legenda).

### Patrocinadores

`.v3revent-sponsors` · `.v3revent-sponsors-group` · `.v3revent-sponsors-group-title` · `.v3revent-sponsors-grid` · `.v3revent-sponsors-item` · `.v3revent-sponsors-link` · `.v3revent-sponsors-logo` · `.v3revent-sponsors-name`.

### Compartilhar

`.v3revent-share` · `.v3revent-share-trigger` (variante `--copied`) · `.v3revent-share-networks` · `.v3revent-share-network` (variantes `--whatsapp`, `--facebook`, `--linkedin`, cada uma com a cor da rede).

### Documentos anexos

`.v3revent-documents` · `.v3revent-documents-title` · `.v3revent-documents-list` · `.v3revent-documents-link` · `.v3revent-documents-ext` (etiqueta da extensão do arquivo).

---

## Exemplos práticos

**Deixar o botão de compra em pílula e em caixa-alta:**

```css
.v3revent-btn--cta {
  border-radius: 999px;
  text-transform: uppercase;
  letter-spacing: .04em;
}
```

**Dar mais respiro entre as seções da página do evento:**

```css
:root {
  --v3revent-section-gap: 3rem;
}
```

**Destacar a faixa de preço ativa com um fundo suave:**

```css
.v3revent-tier-item.active {
  background: color-mix(in srgb, var(--v3revent-secondary) 12%, transparent);
}
```

**Dar um leve tom aos campos do formulário (em vez do branco padrão):**

```css
:root {
  --v3revent-field-bg: #f4f6f8;
}
```

---

## Boas práticas

{: .tip }
> - **Sobrescreva variáveis** sempre que possível — é o que menos quebra em atualizações.
> - **Só redefina regras de classe** quando a variável não cobrir o ajuste. Nesse caso, mantenha o seletor simples (uma classe) e evite depender do aninhamento do HTML.
> - **Restrinja o escopo** ancorando em `.v3revent-registration-wrap` (formulário) ou `.v3revent-page` (página do evento) para não afetar o resto do site.
> - **Teste no claro e no escuro** quando o evento usar o modo escuro na página.
> - **Revise após cada atualização** do plugin: se um estilo seu deixou de fazer efeito, é sinal de que a estrutura interna mudou.

## Precisa de ajuda?

Se você quer um ajuste e não encontrou a classe ou a variável certa, fale com a gente pelo **[Ajuda e Feedback](/modulos/ajuda-e-feedback/)** — é útil informar qual tela e qual elemento você quer personalizar.
