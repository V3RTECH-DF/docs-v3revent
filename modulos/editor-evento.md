---
title: Editor de evento
parent: Módulos
nav_order: 3
---

# Editor de evento

O editor concentra toda a configuração de um evento, organizado em abas na ordem natural de preenchimento. Você abre o editor ao criar um evento (**Novo Evento**) ou clicar em **Editar** na lista. Ao terminar, use **Salvar** no rodapé; ao mudar o status para publicado, o evento vai ao ar e ganha um produto no WooCommerce.

No topo do editor, o botão **Ver página** abre a página pública do evento em uma nova aba. Enquanto o evento está em rascunho, ele vira **Pré-visualizar** (mostra a página só para você). Veja **[Página do evento](/modulos/pagina-do-evento/)**.

A sequência das abas é: **Detalhes → Programação → Campos do Formulário → Preços → Aparência → Página → Credencial → Certificado → Avaliação → Patrocinadores → Relatório → WooCommerce → Equipe**.

## Detalhes

Os dados básicos do evento.

![Aba Detalhes do editor de evento](/assets/screenshots/evento-editor-detalhes.png)

- **Título**;
- **Descrição do evento** — texto de apresentação, com **editor de formatação** (veja abaixo);
- **Data/hora de início** (obrigatória) e **de término**;
- **Local** e **link do local**;
- **Capacidade total** (0 = ilimitada);
- **Máximo de inscritos por pedido**;
- **Inscrições abertas** (liga/desliga o formulário);
- **Data de abertura das inscrições** (opcional) — antes dela, o formulário fica indisponível e a página mostra um aviso de **"Inscrições em breve"** (veja abaixo);
- **Data limite de inscrições** (opcional) — após esta data, as inscrições **fecham sozinhas**;
- **Tipo de inscrição** — controla a seção "Responsável pela inscrição" no formulário (veja abaixo);
- **Exibir contato dos organizadores na página** (opcional) — mostra um cartão "Fale com a organização" na página do evento (veja abaixo);
- **Contagem regressiva na página** (opcional) — mostra contadores para o início do evento e o fim das inscrições (veja abaixo);
- **Status** do evento.

### Aviso e data de abertura das inscrições

A página do evento mostra automaticamente, num **cartão logo abaixo do topo**, quando as inscrições **não estão abertas** — assim o visitante entende o momento em vez de simplesmente não ver o formulário:

- **Inscrições em breve** — antes da **data de abertura**. Se você informou a data, o aviso mostra **quando as inscrições abrem**.
- **Inscrições encerradas** — depois da **[data limite de inscrições](#detalhes)**.
- **Inscrições indisponíveis no momento** — quando você **desligou** as inscrições manualmente (**Inscrições abertas** desmarcado).

<!-- print pendente: evento-editor-inscricoes-aviso.png — aba Detalhes com o campo "Data de abertura das inscrições" ao lado da "Data limite de inscrições", viewport desktop -->

O campo **Data de abertura das inscrições** é o par simétrico da **data limite**: **antes** dela a página exibe "Em breve" e o formulário fica bloqueado; **depois** dela (e até a data limite, se houver) as inscrições ficam abertas. **Se você deixar a data de abertura em branco, as inscrições já começam abertas** — nada muda em relação ao comportamento de sempre.

{: .note }
> As duas datas trabalham juntas: **abertura** programa o início e **limite** programa o fim. Com as duas preenchidas, você define a **janela de inscrição** inteira e não precisa lembrar de ligar nem desligar o formulário — o sistema cuida das duas pontas.

### Contato dos organizadores

Ligue **Exibir contato dos organizadores na página** para mostrar um cartão **"Fale com a organização"** na página do evento, com os canais de atendimento. Ao ligar o toggle, preencha os campos que quiser divulgar:

- **E-mail**;
- **WhatsApp** — informe o número **com o código do país** (ex.: `55` para o Brasil), para que o botão abra a conversa corretamente;
- **Telefone**.

Só os campos **preenchidos** aparecem na página — deixe em branco o que não quiser divulgar. O cartão é opcional: com o toggle desligado, nada aparece.

<!-- print pendente: evento-editor-contato-organizadores.png — aba Detalhes com o toggle "Exibir contato dos organizadores" ligado e os campos e-mail/WhatsApp/telefone, viewport desktop -->



{: .tip }
> Use um canal que a organização realmente acompanha durante o período de inscrições. Um contato visível reduz dúvidas e aumenta a confiança de quem vai pagar a inscrição.

### Contagem regressiva

Ligue **Contagem regressiva na página** para exibir contadores que atualizam **ao vivo** (dias, horas, minutos e segundos). Há um toggle para cada contador:

- **Início do evento** — conta o tempo que falta para o evento começar.
- **Fim das inscrições** — conta o tempo que falta para a **data limite de inscrições**.

Cada contador só aparece se a **data correspondente estiver preenchida** e ainda for **futura**. Um contador cuja data já passou simplesmente não é exibido.

<!-- print pendente: evento-editor-contagem-regressiva.png — aba Detalhes com os toggles "Contagem regressiva na página" (início do evento e fim das inscrições), viewport desktop -->



{: .tip }
> O contador de **fim das inscrições** cria senso de urgência e costuma acelerar a decisão de quem está em dúvida — combine-o com a **[data limite](#detalhes)**.

### Descrição do evento

A descrição usa um **editor com formatação** (o mesmo editor do WordPress): você aplica **negrito**, *itálico*, listas, títulos, citações e links, alterna entre as abas **Visual** e **Texto** (HTML), e pode **inserir imagens** pelo botão **Adicionar mídia**. O que você escrever aqui aparece na **página pública do evento**. Se deixar a descrição em branco, ela simplesmente não aparece na página.

![Editor de descrição do evento com barra de formatação](/assets/screenshots/evento-editor-descricao.png)

### Tipo de inscrição

Define se o formulário pede os **Dados do Responsável pela Inscrição**:

- **O participante escolhe** (padrão) — o formulário mostra a pergunta "Para quem é esta inscrição?" (Somente para mim / Para um grupo de pessoas) e revela o responsável só quando é para um grupo. Melhor opção para a maioria dos eventos, em que quase todos se inscrevem sozinhos, mas alguns podem inscrever um grupo.
- **Somente individual** — esconde a seção do responsável. Use quando cada pessoa sempre faz a própria inscrição.
- **Sempre em grupo (com responsável)** — mostra o responsável direto, como passo obrigatório. Use em eventos em que quem inscreve costuma ser uma empresa/escola cadastrando várias pessoas.

![Seletor "Tipo de inscrição" na aba Detalhes](/assets/screenshots/evento-editor-tipo-inscricao.png)

{: .tip }
> Deixe **Inscrições abertas** desligado enquanto ainda está montando o evento. Ligue só quando tudo estiver conferido.

{: .note }
> A **data limite** é o jeito de programar o encerramento: informe a data e não precisa lembrar de desligar as inscrições no dia — o sistema fecha o formulário automaticamente quando ela passa. Deixe em branco para não ter limite por data.

## Documentos

Na aba **Documentos** você anexa arquivos ao evento — **regulamento**, **kit do participante** e o que mais fizer sentido —, cada um com um **título**. Eles aparecem como **links de download** na página do evento.

- Clique em **Adicionar documentos** e escolha um ou mais arquivos na biblioteca de mídia (aceita PDF, DOCX e outros formatos).
- Dê um **título** a cada documento (é o texto que o visitante vê no link), **reordene** com as setas e **remova** com a lixeira.
- Em **Título da seção**, defina como o bloco se chama na página (ex.: *"Documentos complementares"*, *"Leia mais"*). Em branco, aparece como **"Documentos"**.
- Em **Exibir na página do evento**, escolha onde a lista aparece: **antes** do formulário de inscrição (padrão), **depois** da inscrição, **logo após as informações** do evento, ou **não exibir**.

Na página, os documentos aparecem em uma **grade** (vários por linha, até preencher a largura) e a seção usa a **mesma largura do formulário de inscrição**, para um alinhamento consistente.

![Aba Documentos do editor de evento](/assets/screenshots/evento-editor-documentos.png)

{: .tip }
> Coloque o **regulamento antes do formulário de inscrição** — assim o participante lê as regras antes de confirmar. Você também pode inserir a lista em qualquer página com o shortcode `[v3revent_documents]`.

## Programação

As **sessões** do evento (dia, início, fim, título, descrição, palestrante(s), local e trilha). Você adiciona, reordena e remove cards de sessão. A programação aparece na página pública do evento e no bloco/shortcode correspondente.

![Aba Programação do editor de evento](/assets/screenshots/evento-editor-programacao.png)

## Campos do Formulário

Define **quais dados coletar de cada participante**. Cada campo é um card com **id**, **rótulo**, **tipo**, **obrigatório**, **placeholder**, **opções** (para seleção/múltipla escolha) e **ordem** (arraste para reordenar).

![Aba Campos do Formulário do editor de evento](/assets/screenshots/evento-editor-campos.png)

Tipos disponíveis: texto, e-mail, CPF, telefone, número, **lista (select)**, **opções (radio)**, **checkbox**, área de texto e data. O padrão traz nome, CPF, e-mail, organização e telefone.

Os tipos **lista** e **opções (radio)** deixam o participante escolher **uma** entre as opções que você definir (uma por linha). O tipo **checkbox** tem dois comportamentos:

- **Sem opções** — um único checkbox de **sim/não** (ex.: "Aceito receber novidades").
- **Com opções** — vira **múltipla escolha**: o participante pode marcar **mais de uma** (ex.: restrições alimentares: Vegetariano, Vegano, Sem lactose). Cada opção aparece em sua própria linha; se marcar o campo como obrigatório, o participante precisa escolher ao menos uma.

{: .important }
> **Minimização (LGPD):** só torne obrigatório o que você realmente vai usar. Cada dado a mais é uma responsabilidade a mais sob a LGPD — e um formulário mais longo converte menos.

## Preços

A aba **Preços** traz **três chaves de preço independentes**, que você liga conforme a necessidade do evento e pode **combinar** à vontade:

- **Preço por lote (data)** — o valor muda por **janelas de data** (lotes); cobra o lote vigente na **data da inscrição**. Ideal para corridas e eventos com "1º lote / 2º lote / 3º lote".
- **Preço por modalidade** — cada inscrito paga conforme a **opção escolhida** no formulário (ex.: Estudante / Profissional). Requer um **campo de opção única** na aba **Campos do Formulário**.
- **Desconto por quantidade** — o preço por inscrito cai em **faixas**, conforme o **número de inscritos** do pedido (quanto mais gente, menor o valor por inscrito).

![Aba Preços com as três chaves independentes](/assets/screenshots/evento-editor-precos.png)

{: .note }
> **Ligar uma chave só = como era antes.** Cada chave funciona sozinha, exatamente como funcionava. E **eventos que já existiam continuam iguais**, sem precisar reconfigurar nada — só mexa aqui se quiser aproveitar a combinação.

### Combinar as chaves

Você pode ligar **qualquer combinação**. Por exemplo: um evento com **1º e 2º lote** (por data), em que cada lote tem preços por **modalidade** (Estudante × Profissional) e ainda dá **desconto por quantidade** a partir de 5 inscritos.

Quando **Preço por lote** está ligado, cada lote passa a ter o **seu próprio bloco de preços** — as faixas de quantidade e/ou as tabelas por modalidade daquele lote. Assim, o 1º lote pode ter valores diferentes do 2º, com a mesma estrutura de modalidades e faixas.

{: .tip }
> **Botão "Duplicar lote".** Para não reconfigurar tudo lote a lote, monte um lote por completo e use **Duplicar lote**: ele copia a configuração inteira (faixas e tabelas por modalidade) para um novo lote, e você só ajusta as **datas** e os **valores**.

### Desconto por quantidade

As **faixas por quantidade**: para cada faixa, a quantidade mínima, a máxima (última em branco = "acima de"), o preço por inscrito e um rótulo.

{: .important }
> **O desconto é destravado pelo total de inscritos do pedido — não por categoria.** Num pedido com **5 Estudantes + 3 Profissionais** (8 no total), **todos** entram na faixa "a partir de 5": cada inscrito paga o preço dessa faixa **na sua própria categoria**. Ou seja, a quantidade que conta é a do pedido inteiro, mesmo com modalidades misturadas.

### Preço por modalidade

Use quando o evento tem **perfis com preços diferentes** — por exemplo, uma corrida com valores por categoria, ou um encontro com preços para "Estudante", "Profissional" e "Convidado".

Para configurar:

1. Ligue **Preço por modalidade**.
2. Em **Campo de preço (modalidade)**, escolha o **campo de opção única** do formulário que define a modalidade de cada inscrito (um campo do tipo **lista** ou **opções**, criado na aba **Campos do Formulário**).
3. Cada opção do campo ganha a sua **própria tabela de preços**. Preencha os valores de cada modalidade; opções sem tabela própria usam a **Tabela base** como padrão.

![Preço por modalidade: campo designado e tabela por opção](/assets/screenshots/evento-editor-precos-modalidade.png)

{: .note }
> Se o formulário ainda não tem um campo de opção única, o editor avisa e indica criar um na aba **Campos do Formulário** — ele é quem define as modalidades disponíveis.

### Preço por lote (data)

Ligue **Preço por lote (data)** e cadastre os **lotes** — cada um com **data de início**, **data de fim** e um **rótulo** (ex.: "1º lote"). Use as setas para reordenar e o **+** para adicionar lotes.

![Aba Preços no modo por lote de data](/assets/screenshots/evento-editor-precos-lote.png)

O sistema cobra sempre o **lote vigente na data em que a pessoa se inscreve** — você não precisa trocar o preço na virada de cada lote, é automático. Quem se inscreve mais cedo paga o lote mais barato.

Como cada lote tem o **seu próprio bloco de preços**, você define ali as faixas e/ou as tabelas por modalidade daquele lote (veja **[Combinar as chaves](#combinar-as-chaves)** e o botão **Duplicar lote**).

{: .tip }
> **Case o último lote com a data limite.** Se ninguém estiver num lote vigente (antes do 1º ou depois do último), as inscrições ficam indisponíveis. Combine o fim do último lote com a **[Data limite de inscrições](#detalhes)** (aba Detalhes) para o encerramento ficar claro.

## Aparência

A identidade visual do evento, que se aplica ao formulário, à página, aos e-mails, ao recibo e à credencial:

![Aba Aparência do editor de evento](/assets/screenshots/evento-editor-aparencia.png)

- **Logo do evento** (pela Biblioteca de Mídia) e a **posição** dela na página do evento (ver abaixo);
- **Cores do evento** (ver abaixo);
- **Fonte**;
- **Galeria de imagens** do evento (com legendas), exibida na página pública.

### Posição da logo na página do evento

O seletor **Posição da logo na página do evento** define **onde** a logo do evento aparece na página pública (no layout **[Página do plugin](/modulos/pagina-do-evento/)**):

- **No topo da página (destaque)** (padrão) — a logo aparece **em destaque no alto da página**, antes do hero.
- **Abaixo do hero** — a logo aparece logo depois do topo, no início do conteúdo.
- **Junto das informações** — a logo acompanha o bloco de **informações** do evento.
- **Não mostrar na página** — a página do evento **não** exibe a logo.

A logo é sempre exibida sobre um **cartão branco**, para ficar legível em qualquer tema e tanto no modo claro quanto no escuro — inclusive logos com fundo transparente ou feitas para fundo claro.

{: .note }
> **"Não mostrar na página" tira a logo só da página.** Mesmo com essa opção, a logo continua saindo normalmente nos **relatórios**, **e-mails** e **credenciais** — ela apenas deixa de aparecer na página pública do evento.

### Tamanho da logo na página

Logo abaixo da posição, o seletor **Tamanho da logo na página** controla o quanto a logo do evento aparece na página pública (também no layout **[Página do plugin](/modulos/pagina-do-evento/)**):

- **Pequeno**;
- **Médio** (padrão);
- **Grande**;
- **Personalizado** — você define o tamanho exato.

No modo **Personalizado**, informe **a largura _ou_ a altura** (entre **40 e 600 px**) — a **outra dimensão é calculada automaticamente**, mantendo a **proporção** original da imagem, sem distorção.

{: .note }
> Eventos que já existiam continuam no tamanho **Médio**; ajuste aqui só se quiser mudar. A logo continua sempre sobre o **cartão branco** — o tamanho muda apenas o quanto ela ocupa.

### Cores do evento

Por padrão, o evento **herda as cores globais** definidas em **[Configurações → Aparência](/modulos/configuracoes/)** — você não precisa configurar nada evento a evento. Alterar as cores globais atualiza automaticamente todos os eventos que estão herdando.

Se um evento específico precisa de cores próprias, clique em **Personalizar para este evento** e ajuste a cor primária e a secundária. Para voltar a seguir o padrão global, use **Voltar a usar as cores globais**.

## Página

Escolhe como o evento é exibido publicamente: o **layout** e o **modelo visual** da página do evento (uma página inteira do plugin, com hero, informações, programação e formulário). Veja **[Página do evento](/modulos/pagina-do-evento/)**.

![Aba Página do editor de evento](/assets/screenshots/evento-editor-pagina.png)

### Escolher o layout

O **layout** decide **como a página do evento se encaixa no seu site**:

- **Tema do site** — a página do evento aparece **dentro do seu site**, com o **cabeçalho e o rodapé do tema** (menu, logo do site, rodapé) ao redor do conteúdo do evento. Use quando quiser que o evento faça parte da navegação do site.
- **Página do plugin** — a página do evento aparece em **tela cheia** (formato *hotsite* / *onepage*), **sem o cabeçalho e o rodapé do tema**: só o conteúdo do evento, ocupando a tela inteira. É a opção para uma página de divulgação focada, que abre limpa e vai direto ao evento e à inscrição. É neste layout que valem a **galeria de modelos**, o **esquema de cor** e o **Hero** (abaixo).

{: .note }
> **Mudou na v1.39.0:** no layout **Página do plugin**, a página agora aparece **em tela cheia, sem o cabeçalho e o rodapé do site**. Se você prefere manter o cabeçalho e o rodapé do seu tema ao redor do evento, use o layout **Tema do site**.

### Escolher o modelo da página

Quando o layout é **Página do plugin**, você escolhe o **modelo** numa **galeria** — cada modelo tem uma personalidade própria (tipografia, formas, acento e espaçamento), e **as cores vêm do seu evento**:

![Galeria de modelos de página, com o toggle de esquema de cor](/assets/screenshots/pagina-galeria-modelos.png)

Os 6 modelos:

- **Moderno** — equilibrado e versátil, bom para a maioria dos eventos.
- **Compacto** — denso e direto, em fundo escuro; vai direto à inscrição.
- **Vibrante** — lúdico e animado (cantos arredondados), para jogos, brincadeiras, público jovem ou infantil.
- **Clássico** — formal e elegante, com fonte serifada, para congressos e eventos científicos.
- **Minimalista** — limpo, com muito respiro e sem enfeites.
- **Energia** — dinâmico e marcante, em fundo escuro, para corridas e eventos esportivos.

Cada card mostra uma **prévia** do visual. Clique no modelo desejado e **Salve**.

#### Esquema de cor: claro, escuro ou do sistema

Logo abaixo da galeria, o **Esquema de cor** vale para **qualquer** modelo:

- **Claro** — fundo claro.
- **Escuro** — fundo escuro.
- **Sistema** — segue a preferência do **aparelho de cada visitante** (quem usa o celular no modo escuro vê a página escura, e vice-versa).
- **Automático** — usa o padrão do modelo escolhido.

Todos os modelos foram ajustados para ter **bom contraste** nos dois modos.

### Hero (topo da página)

O **Hero** é o destaque no topo da página do evento. Você escolhe **como ele aparece**, no seletor **Hero (topo da página)** — disponível quando o layout é a **página do plugin**:

![Seletor de modo do Hero e campo Imagem do Hero, na aba Página](/assets/screenshots/evento-editor-hero.png)

- **Só imagem** — mostra a **arte inteira, sem cortar**, sem nenhum texto por cima. **Ideal quando a arte de divulgação já traz os dados do evento** (nome, data, local). É a opção certa para não sobrepor textos e não perder informação, inclusive no celular.
- **Imagem + texto** — usa a arte como **fundo** e sobrepõe **título, data e local** com um escurecimento para dar contraste. Boa para uma **foto** de fundo sobre a qual você quer exibir os dados do evento.
- **Só texto** — sem imagem: título, data e local sobre um fundo nas **cores do evento**.
- **Automático (pelo tema)** — deixa o tema decidir (é o padrão; mantém o comportamento de sempre).

Em **Imagem do Hero**, escolha a arte do topo. Se deixar vazio, o Hero usa a **1ª foto da galeria**; se o evento não tiver nenhuma imagem, o topo aparece no modo **"só texto"** (nome, data e local sobre as cores do evento).

Veja como fica o modo **Só imagem** na página pública — a arte aparece por inteiro:

![Página do evento com o Hero no modo "Só imagem" — arte integral](/assets/screenshots/pagina-hero-so-imagem.png)

{: .tip }
> **Tem uma arte de divulgação com os dados já embutidos?** Use **Só imagem** — assim a arte aparece inteira e legível, sem os textos do plugin por cima. O modo **Imagem + texto** é para quando o fundo é uma **foto** e você quer que o plugin escreva o nome/data/local em cima.

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
