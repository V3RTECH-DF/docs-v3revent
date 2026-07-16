---
title: Editor de evento
parent: Módulos
nav_order: 3
---

# Editor de evento

O editor concentra toda a configuração de um evento, organizado em abas na ordem natural de preenchimento. Você abre o editor ao criar um evento (**Novo Evento**) ou clicar em **Editar** na lista. Ao terminar, use **Salvar** no rodapé; ao mudar o status para publicado, o evento vai ao ar e ganha um produto no WooCommerce.

A sequência das abas é: **Detalhes → Programação → Campos do Formulário → Tabela de Preços → Aparência → Página → Credencial → Certificado → Avaliação → Patrocinadores → Relatório → WooCommerce → Equipe**.

## Detalhes

Os dados básicos do evento.

![Aba Detalhes do editor de evento](/assets/screenshots/evento-editor-detalhes.png)

- **Título**;
- **Data/hora de início** (obrigatória) e **de término**;
- **Local** e **link do local**;
- **Capacidade total** (0 = ilimitada);
- **Máximo de inscritos por pedido**;
- **Inscrições abertas** (liga/desliga o formulário);
- **Data limite de inscrições** (opcional) — após esta data, as inscrições **fecham sozinhas**;
- **Status** do evento.

{: .tip }
> Deixe **Inscrições abertas** desligado enquanto ainda está montando o evento. Ligue só quando tudo estiver conferido.

{: .note }
> A **data limite** é o jeito de programar o encerramento: informe a data e não precisa lembrar de desligar as inscrições no dia — o sistema fecha o formulário automaticamente quando ela passa. Deixe em branco para não ter limite por data.

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

No topo da aba há o **Modo de preço**, que define como o valor da inscrição é calculado:

- **Por quantidade (faixas)** — o preço por inscrito varia com o **número de inscritos** no pedido (quanto mais gente, menor o valor por inscrito).
- **Por lote (data)** — o preço é definido por **janelas de data** (lotes); cobra o lote ativo **na data da inscrição**. Ideal para corridas e eventos com "1º lote / 2º lote / 3º lote".

![Aba Tabela de Preços do editor de evento](/assets/screenshots/evento-editor-precos.png)

### Por quantidade (faixas)

As **faixas por quantidade**: para cada faixa, a quantidade mínima, a máxima (última em branco = "acima de"), o preço por inscrito e um rótulo.

### Por lote (data)

No modo **Por lote (data)**, você cadastra os **lotes** — cada um com uma **data de início**, uma **data de fim**, um **preço por inscrito** e um **rótulo** (ex.: "1º lote"). Use as setas para reordenar e o **+** para adicionar lotes.

![Aba Tabela de Preços no modo por lote de data](/assets/screenshots/evento-editor-precos-lote.png)

O sistema cobra sempre o **lote ativo na data em que a pessoa se inscreve** — você não precisa trocar o preço na virada de cada lote, é automático. Quem se inscreve mais cedo paga o lote mais barato.

{: .tip }
> **Case o último lote com a data limite.** No modo por lote, se ninguém estiver num lote ativo (antes do 1º ou depois do último), as inscrições ficam indisponíveis. Combine o fim do último lote com a **[Data limite de inscrições](#detalhes)** (aba Detalhes) para o encerramento ficar claro.

{: .note }
> **Neste modo não há desconto por quantidade** — o preço do lote é por inscrito, multiplicado pela quantidade. Ex.: lote a R$ 100 × 2 inscritos = R$ 200. Para desconto por grupo, use o modo **Por quantidade**.

### Precificação por modalidade

No modo **Por quantidade**, se o evento tem perfis com preços diferentes, designe um **campo de preço** (um select do formulário, ex.: "Modalidade") em que **cada opção tem a sua própria tabela de faixas**. O total é a soma por modalidade, e a faixa de cada opção é definida pela contagem daquela modalidade. Opções sem tabela própria caem na tabela base.

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

## Certificado

Configura o **certificado de participação** dos inscritos elegíveis:

![Aba Certificado do editor de evento](/assets/screenshots/evento-editor-certificado.png)

- **Emitir certificado para este evento** (liga/desliga);
- **Modelo** do certificado (entre os disponíveis — ex.: Clássico e Moderno —, com a logo e as cores do evento);
- **Carga horária** em horas (opcional; 0 = não exibir);
- um **contador de elegíveis** e o botão **Enviar certificados aos elegíveis** (envio manual por e-mail).

Quem é elegível depende da **modalidade** do evento (aba **Detalhes**): em evento **presencial**, quem fez **check-in**; em evento **virtual**, quem tem a inscrição confirmada. Cada certificado tem um **link público de verificação** (`certificado/{código}`), imprimível e com versão em PDF.

{: .note }
> O certificado só é liberado para quem é elegível. Em evento presencial, isso significa que **o check-in no dia alimenta diretamente a emissão** — mais um motivo para credenciar bem.

## Avaliação

Reúne a **pesquisa de avaliação** do evento e a sua retrospectiva, em quatro áreas:

![Aba Avaliação do editor de evento](/assets/screenshots/evento-editor-avaliacao.png)

- **Perguntas** — monte o questionário com tipos prontos: **nota (1–5)**, **NPS (0–10)**, escolha única, múltipla escolha e texto livre;
- **Convites** — envie o convite da pesquisa por e-mail **aos presentes** (com a opção de mandar só para quem ainda não respondeu);
- **Resultados** — os números **de forma anônima**: score NPS, médias das notas, distribuição das escolhas, comentários e taxa de resposta;
- **Retrospectiva** — as suas **lições aprendidas** como coordenador (o que foi bem, o que melhorar, ações para a próxima edição).

A pesquisa é **anônima** e liberada apenas para quem **fez check-in**: cada participante recebe um link próprio (`avaliacao/{código}`), responde sem login, e a resposta **não fica vinculada à pessoa**. Veja **[No dia e depois](/guia-do-gestor/no-dia-e-depois/)**.

## Patrocinadores

Cadastra os **patrocinadores e apoiadores** do evento. A aba é **opcional** — eventos sem patrocinadores ficam em branco.

![Aba Patrocinadores do editor de evento](/assets/screenshots/evento-editor-patrocinadores.png)

Cada patrocinador tem:

- **Nome** e **CNPJ/CPF** (aceita o CNPJ alfanumérico);
- **Logomarca** (pela Biblioteca de Mídia) e **site**;
- **Tipo** (patrocínio, apoio, realização, parceria);
- **Valor**, com a **natureza** (dinheiro ou permuta) e a **situação** (previsto, confirmado, recebido);
- **Contrapartidas** negociadas — uma lista pronta de caixas de seleção (marca no material, naming space, fala ao vivo, stand, menção em redes, logo no site, brinde) mais um campo livre.

Você reordena e remove patrocinadores à vontade. Na **página pública** do evento, aparecem apenas o **logo, o nome e o tipo** (agrupados por tipo) — valores, situação, contrapartidas e documento ficam só no seu controle interno. Esses dados também alimentam o **Relatório** do evento.

## Relatório

Monta o **relatório consolidado do evento em PDF**, com seções **escolhíveis e reordenáveis**:

![Aba Relatório do editor de evento](/assets/screenshots/evento-editor-relatorio.png)

- Ligue/desligue e **reordene** as seções: dados da organização, dados gerais (obrigatória), patrocinadores, programação, inscritos e presença, valores, avaliação, lições aprendidas, texto livre e equipe;
- informe a **meta de arrecadação prevista** (usada no comparativo previsto × arrecadado);
- escreva um **texto livre** do coordenador;
- **Salvar configuração** guarda as escolhas; **Gerar Relatório (PDF)** baixa o documento na hora, com os dados atuais.

O relatório é gerado **sob demanda** (não fica armazenado) e é um **download restrito ao painel** — por conter valores, equipe e retrospectiva, não tem link público. Também dá para gerá-lo pelo ícone de relatório na **[lista de eventos](/modulos/eventos/)**. Veja **[No dia e depois](/guia-do-gestor/no-dia-e-depois/)**.

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
