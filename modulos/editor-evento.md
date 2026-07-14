---
title: Editor de evento
parent: Módulos
nav_order: 3
---

# Editor de evento

O editor concentra toda a configuração de um evento, organizado em abas na ordem natural de preenchimento. Você abre o editor ao criar um evento (**Novo Evento**) ou clicar em **Editar** na lista. Ao terminar, use **Salvar** no rodapé; ao mudar o status para publicado, o evento vai ao ar e ganha um produto no WooCommerce.

A sequência das abas é: **Detalhes → Programação → Campos do Formulário → Tabela de Preços → Aparência → Página → Credencial → WooCommerce → Equipe**.

## Detalhes

Os dados básicos do evento.

![Aba Detalhes do editor de evento](/assets/screenshots/evento-editor-detalhes.png)

- **Título**;
- **Data/hora de início** (obrigatória) e **de término**;
- **Local** e **link do local**;
- **Capacidade total** (0 = ilimitada);
- **Máximo de inscritos por pedido**;
- **Inscrições abertas** (liga/desliga o formulário);
- **Status** do evento.

{: .tip }
> Deixe **Inscrições abertas** desligado enquanto ainda está montando o evento. Ligue só quando tudo estiver conferido.

## Programação

As **sessões** do evento (dia, início, fim, título, descrição, palestrante(s), local e trilha). Você adiciona, reordena e remove cards de sessão. A programação aparece na página pública do evento e no bloco/shortcode correspondente.

![Aba Programação do editor de evento](/assets/screenshots/evento-editor-programacao.png)

## Campos do Formulário

Define **quais dados coletar de cada participante**. Cada campo é um card com **id**, **rótulo**, **tipo**, **obrigatório**, **placeholder**, **opções** (para seleção/múltipla escolha) e **ordem** (arraste para reordenar).

![Aba Campos do Formulário do editor de evento](/assets/screenshots/evento-editor-campos.png)

Tipos disponíveis: texto, e-mail, CPF, telefone, número, seleção (select), múltipla escolha (radio), caixas (checkbox), área de texto e data. O padrão traz nome, CPF, e-mail, organização e telefone.

{: .important }
> **Minimização (LGPD):** só torne obrigatório o que você realmente vai usar. Cada dado a mais é uma responsabilidade a mais sob a LGPD — e um formulário mais longo converte menos.

## Tabela de Preços

As **faixas por quantidade**: para cada faixa, a quantidade mínima, a máxima (última em branco = "acima de"), o preço por inscrito e um rótulo.

![Aba Tabela de Preços do editor de evento](/assets/screenshots/evento-editor-precos.png)

### Precificação por modalidade

Se o evento tem perfis com preços diferentes, designe um **campo de preço** (um select do formulário, ex.: "Modalidade") em que **cada opção tem a sua própria tabela de faixas**. O total é a soma por modalidade, e a faixa de cada opção é definida pela contagem daquela modalidade. Opções sem tabela própria caem na tabela base.

## Aparência

A identidade visual do evento, que se aplica ao formulário, à página, aos e-mails, ao recibo e à credencial:

![Aba Aparência do editor de evento](/assets/screenshots/evento-editor-aparencia.png)

- **Logo do evento** (pela Biblioteca de Mídia);
- **Cor primária** e **secundária** (seletor de cor);
- **Fonte**;
- **Galeria de imagens** do evento (com legendas), exibida na página pública.

Essas escolhas sobrepõem o padrão global definido em **[Configurações → Aparência](/modulos/configuracoes/)**.

## Página

Escolhe como o evento é exibido publicamente: o **layout** e o **tema visual** da página do evento (uma página inteira do plugin, com hero, informações, programação e formulário). Veja **[Página do evento](/modulos/pagina-do-evento/)**.

![Aba Página do editor de evento](/assets/screenshots/evento-editor-pagina.png)

## Credencial

Configura o **crachá** de cada participante confirmado:

![Aba Credencial do editor de evento](/assets/screenshots/evento-editor-credencial.png)

- **Modelo** (entre os disponíveis), com a logo e as cores do evento;
- **Envio automático** por e-mail a cada inscrito (opcional);
- **QR e networking**: por padrão, o QR carrega o código de validação; com o consentimento de networking do inscrito, carrega um cartão de contato (vCard) — você mapeia quais campos entram no vCard;
- Texto do **consentimento** de networking.

Veja **[Documentos](/modulos/documentos/)** para como a credencial fica e a geração em lote.

## WooCommerce

Mostra o **produto vinculado** ao evento (criado automaticamente ao publicar) e o **shortcode** do formulário — ex.: `[v3revent_registration event_id="123"]` — com um botão para copiar.

![Aba WooCommerce do editor de evento](/assets/screenshots/evento-editor-woocommerce.png)

{: .note }
> Você não precisa editar esse produto no WooCommerce: ele é oculto do catálogo e tem o preço controlado pelas faixas do evento. Mexer nele manualmente pode causar inconsistências.

## Equipe

Define quem trabalha **neste evento** e com qual papel:

![Aba Equipe do editor de evento](/assets/screenshots/evento-editor-equipe.png)

- Busque um usuário do WordPress e atribua **Coordenador de Eventos** (gestão completa do evento) ou **Equipe de Evento** (operacional, faz check-in).

Veja os papéis e o alcance de cada um em **[Primeiros passos](/primeiros-passos/)**.
