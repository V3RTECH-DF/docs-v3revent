---
title: Novidades
nav_order: 7
---

# Novidades

O que mudou no V3REvent, em linguagem simples — **da mais recente para a mais antiga**. Cada novidade traz a **versão** em que foi introduzida, para você saber o que é realmente novo.

{: .note }
> A versão instalada aparece no cabeçalho do painel do V3REvent (ex.: `v1.32.0`). Compare com a lista abaixo para ver o que você já tem.

---

## Controles de tamanho de texto dentro do topo do evento
**v1.55.0 · julho de 2026**

Os controles de acessibilidade **A− / A / A+** deixaram de ocupar uma faixa de largura inteira no topo da página e agora aparecem numa **caixinha discreta no canto superior direito do topo do evento (hero)** — economizando espaço e mantendo o recurso à mão. A caixinha é translúcida e legível sobre qualquer tipo de topo (imagem, imagem+texto ou só texto), no tema claro ou escuro; no **celular**, fica compacta no canto sem cobrir o título. O funcionamento é o mesmo (aumenta/diminui o conteúdo, memoriza a escolha, liga/desliga na aba **Aparência**). Veja em **[Página do evento](/modulos/pagina-do-evento/#acessibilidade-tamanho-do-texto)**.

## Largura dos campos no formulário
**v1.54.0 · julho de 2026**

Agora você define a **largura de cada campo** do formulário de inscrição: **1 coluna (⅓)**, **2 colunas (⅔)** ou **3 colunas (linha inteira)**. Na aba **Campos do Formulário**, cada campo tem a opção **Largura** — dá para montar linhas compactas (ex.: **Cidade · Estado · CEP** lado a lado) e deixar campos longos, como **Nome completo**, ocupando a linha toda. No **celular** tudo empilha automaticamente. Por padrão os campos começam em **linha inteira**; se você já tinha campos aparecendo lado a lado, eles passam a empilhar até você escolher as larguras (ajuste rápido). Veja em **[Campos do Formulário](/modulos/editor-evento/#largura-do-campo)**.

## Correção: texto invisível ao digitar no formulário (tema escuro)
**v1.53.2 · julho de 2026**

Corrigimos um problema de legibilidade no **formulário de inscrição** quando o **tema do seu site** usa fundo escuro: em alguns casos, o texto que a pessoa **digitava** nos campos (texto, área de texto e listas de seleção) ficava **invisível** — texto escuro sobre fundo escuro. Agora o formulário mantém o fundo e a cor do texto sempre combinando, prevalecendo sobre o tema do site, e o conteúdo digitado volta a aparecer com clareza, tanto no modo claro quanto no escuro. (Complementa o ajuste das listas de seleção feito na v1.49.1.)

## Correção: campo de envio de arquivos aparecendo
**v1.53.1 · julho de 2026**

Logo após lançarmos o **campo de arquivo (upload)**, ele podia aparecer **sem o botão de anexar** na página pública, mostrando só o rótulo. Corrigido: o botão para escolher o arquivo agora aparece normalmente no formulário. Se você criou um campo de arquivo e ele parecia não funcionar, basta atualizar para esta versão.

## Campo de envio de arquivos
**v1.53.0 · julho de 2026**

O formulário agora tem um tipo de campo **Arquivo (upload)**: o inscrito pode **enviar documentos** (laudo, comprovante, etc.). Na aba **Campos do Formulário**, escolha o tipo **Arquivo** e defina os **tipos aceitos**, o **tamanho máximo** e se permite **um ou vários** arquivos. Os arquivos ficam **guardados de forma privada** e só você (ou quem tem permissão no evento) baixa, pela aba **Relatórios**. Tudo com segurança e conforme a LGPD — os arquivos são apagados junto com os dados do inscrito.

## Campos condicionais no formulário
**v1.52.0 · julho de 2026**

Agora você pode fazer um campo do formulário **aparecer só quando fizer sentido**. Na aba **Campos do Formulário**, cada campo tem uma seção **Condições de exibição**: por exemplo, mostrar **"Nome do guia"** apenas quando **"Precisa de guia?" = Sim**. Dá para **combinar várias condições** (exigindo **todas** ou **qualquer uma**) e usar **igual a** / **diferente de**. Um campo oculto pela condição não é exigido nem gravado. Formulários mais curtos e inteligentes, sem pedir o que não se aplica.

## Controle de tamanho do texto (acessibilidade)
**v1.51.0 · julho de 2026**

A página do evento passa a oferecer controles **A− / A / A+** para o visitante **aumentar ou diminuir o tamanho** do conteúdo — uma ajuda de acessibilidade para quem tem baixa visão. A preferência fica **lembrada** no navegador dele. Vem **ligado por padrão**; se quiser, você desliga por evento na aba **Aparência** do editor. (Vale no layout **"Página do Plugin"**.) _Na v1.55.0 esses controles passaram para uma caixinha discreta no canto do topo do evento._

## Preço por modalidade mais simples
**v1.50.0 · julho de 2026**

Ficou mais fácil definir um preço por **modalidade** (ex.: um valor com desconto para PCD). Quando o evento **não** usa desconto por quantidade, cada modalidade agora mostra um **campo simples "Preço (R$)"** — é só digitar o valor, sem precisar montar "faixas" nem ligar o desconto por quantidade. Vale tanto no evento quanto em cada **lote**. Deixando em branco, a modalidade usa o **valor base**. Eventos que já usavam faixas por quantidade continuam funcionando igual.

## Gradientes de fundo na descrição do evento
**v1.49.0 · julho de 2026**

Agora dá para usar **gradientes CSS** de fundo na **descrição do evento** — um ou vários na mesma caixa — para montar heros coloridos, faixas e efeitos decorativos direto pelo editor, sem precisar de imagem. Antes o WordPress descartava esses fundos (só aceitava um gradiente simples). Continua tudo seguro: imagens externas e trechos perigosos seguem bloqueados. Veja exemplos em **[Personalizar com CSS](/modulos/personalizar-css/)**.

## Documentos com layout melhor e título personalizável
**v1.48.0 · julho de 2026**

A seção de **Documentos** na página do evento ficou mais organizada:

- Os documentos agora aparecem em **grade** (vários por linha, preenchendo a largura) em vez de um por linha.
- A seção usa a **mesma largura do formulário de inscrição** — o mesmo vale para os **Patrocinadores** —, alinhando tudo na página.
- O **título** da seção segue o mesmo estilo do título do formulário.
- Você pode **personalizar o título** da seção na aba **Documentos** do editor (ex.: "Documentos complementares", "Leia mais"). Em branco, continua "Documentos".

## Título no formulário de inscrição
**v1.47.0 · julho de 2026**

O formulário de inscrição agora começa com um **título** — por padrão, **"Inscrição"** — que dá contexto ao bloco, em vez de começar direto na data e no local. As informações de **data e local** logo abaixo também passaram a ficar **centralizadas**. Quem quiser trocar o texto do título (por exemplo, "Garanta sua vaga") pode fazê-lo por personalização; para ocultá-lo, basta deixá-lo vazio.

## Data e local com mais destaque na página do evento
**v1.46.0 · julho de 2026**

Na página do evento, a **data** e o **local** agora aparecem em **destaque e centralizados**, logo abaixo do topo — cada um numa "pílula" com um ícone (calendário e localização). Antes esse trecho ficava pequeno e encostado à esquerda, o que parecia deslocado em telas grandes (Full HD e maiores). A **descrição do evento**, logo abaixo, também passou a ser **centralizada**. Tudo continua legível tanto no tema **claro** quanto no **escuro**, e o local segue clicável quando você informa o link do mapa. Não é preciso configurar nada: a mudança vale automaticamente para as páginas no layout **"Página do Plugin"**.

## Contagem regressiva na página do evento
**v1.44.0 · julho de 2026**

A página do evento pode mostrar uma **contagem regressiva** ao vivo — dias, horas, minutos e segundos que se atualizam sozinhos. Há **dois contadores independentes**, cada um com o seu interruptor na aba **Detalhes** do editor:

- **Início do evento** — quanto falta para o evento começar;
- **Fim das inscrições** — quanto falta para a data limite de inscrições.

Cada contador só aparece se a data correspondente estiver **preenchida** e ainda for **futura** — quando a data passa, o contador some sozinho. O contador de **fim das inscrições** é ótimo para criar urgência na reta final. Veja **[Editor de evento → Detalhes](/modulos/editor-evento/)**.

## Contato dos organizadores na página do evento
**v1.43.0 · julho de 2026**

Agora dá para exibir um cartão **"Fale com a organização"** na página do evento, com os canais de atendimento. Ligue **Exibir contato dos organizadores na página** na aba **Detalhes** e preencha o que quiser divulgar: **e-mail**, **WhatsApp** e **telefone**. Só os campos preenchidos aparecem, e o botão do WhatsApp abre a conversa direto (informe o número **com o código do país**, ex.: `55`). Um contato visível reduz dúvidas e passa confiança a quem vai se inscrever. Veja **[Editor de evento → Detalhes](/modulos/editor-evento/)**.

## Aviso de inscrições e data de abertura
**v1.42.0 · julho de 2026**

Quando as inscrições **não estão abertas**, a página do evento agora mostra um **aviso claro** logo abaixo do topo, em vez de só esconder o formulário:

- **Inscrições em breve** — antes de abrir (mostra a data de abertura, se informada);
- **Inscrições encerradas** — depois da data limite;
- **Inscrições indisponíveis no momento** — quando você fecha as inscrições manualmente.

Para isso, a aba **Detalhes** ganhou o campo **Data de abertura das inscrições**, o par simétrico da **data limite**: antes dela a página mostra "Em breve" e o formulário fica bloqueado; depois, as inscrições abrem sozinhas. Com **abertura** e **limite** preenchidas, você programa a **janela de inscrição** inteira, sem precisar ligar nem desligar o formulário na mão. Se deixar a data de abertura em branco, as inscrições já começam abertas — como sempre foi. Veja **[Editor de evento → Detalhes](/modulos/editor-evento/)**.

## Escolha o tamanho da logo do evento na página
**v1.41.0 · julho de 2026**

Além de escolher **onde** a logo aparece, agora você define o **tamanho dela** na página do evento — na aba **Aparência** do editor, no seletor **Tamanho da logo na página**: **Pequeno**, **Médio** (padrão), **Grande** ou **Personalizado**.

No modo **Personalizado**, você informa **a largura _ou_ a altura** (entre **40 e 600 px**) e a outra dimensão é **calculada automaticamente**, mantendo a proporção da imagem, sem distorção. A logo continua sempre sobre o **cartão branco**. Eventos que já existiam ficam em **Médio** — mude só se quiser. Veja **[Editor de evento → Aparência](/modulos/editor-evento/)**.

## Escolha onde a logo do evento aparece na página
**v1.40.0 · julho de 2026**

Você agora decide **onde a logo do evento aparece** na página do evento — na aba **Aparência** do editor, no seletor **Posição da logo na página do evento**:

- **No topo da página (destaque)** (padrão) — a logo em destaque no alto da página;
- **Abaixo do hero** — a logo logo depois do topo;
- **Junto das informações** — a logo acompanha o bloco de informações;
- **Não mostrar na página** — a página não exibe a logo.

A logo aparece **em destaque, sobre um cartão branco**, para ficar bem legível em qualquer tema e tanto no modo claro quanto no escuro. E se você escolher **Não mostrar na página**, a logo **continua saindo normalmente nos relatórios, e-mails e credenciais** — ela só deixa de aparecer na página do evento. Veja **[Editor de evento → Aparência](/modulos/editor-evento/)**.

## Página do evento em tela cheia (sem cabeçalho e rodapé do site)
**v1.39.0 · julho de 2026**

Quando você escolhe o layout **Página do plugin** (aba **Página** do editor), a página do evento agora aparece em **tela cheia** — um *hotsite* de página única, **sem o cabeçalho e o rodapé do seu tema**. Só o conteúdo do evento, ocupando a tela inteira: uma página de divulgação limpa, que abre focada e vai direto à inscrição.

Se você prefere manter o **cabeçalho e o rodapé do seu site** ao redor do evento, basta usar o layout **Tema do site**. Veja **[Página do evento](/modulos/pagina-do-evento/)**.

## Logos de patrocinadores com melhor contraste
**v1.38.2 · julho de 2026**

Os **logos dos patrocinadores** na página do evento agora aparecem **sempre sobre um fundo branco**, em qualquer tema e também no modo escuro. Antes, no modo escuro, o quadro do patrocinador ficava escuro e logos transparentes (ou feitas para fundo claro) perdiam legibilidade — agora cada logo ganha o seu quadro branco, com bom contraste. Você pode enviar as artes em **PNG com fundo transparente** sem se preocupar. Veja **[Página do evento](/modulos/pagina-do-evento/)**.

## Combine tipos de preço no mesmo evento
**v1.38.0 · julho de 2026**

Agora você pode **combinar tipos de preço** no mesmo evento. A aba **Preços** tem **três chaves independentes**, que você liga como quiser — sozinhas ou juntas:

- **Preço por lote (data)** — o valor muda por janela de data (1º lote, 2º lote…).
- **Preço por modalidade** — cada inscrito paga conforme a categoria escolhida (ex.: Estudante × Profissional).
- **Desconto por quantidade** — o preço por inscrito cai em faixas conforme o número de inscritos.

Dá para usar **qualquer combinação** — por exemplo, lotes por data em que **cada lote** tem preços por modalidade **e** desconto para grupos. Quando o preço é por lote, cada lote ganha o **seu próprio bloco de preços**, e há o botão **Duplicar lote** para copiar tudo e só ajustar as datas e os valores.

Um detalhe importante: o **desconto por quantidade** conta o **total de inscritos do pedido**. Num pedido com 5 Estudantes + 3 Profissionais (8 no total), todos entram na faixa "a partir de 5", cada um pagando o valor dessa faixa na sua categoria. No formulário, quando o preço varia por categoria e/ou quantidade, os valores aparecem como **"Valor base"** e o valor final surge no resumo depois de escolher a categoria e adicionar os participantes.

**Ligar uma chave só funciona igual a antes**, e **eventos que já existiam continuam iguais**, sem reconfigurar nada. Veja **[Editor de evento → Preços](/modulos/editor-evento/)**.

## Nova página do manual: personalizar as telas públicas com CSS
**Manual · julho de 2026**

A pedido de quem usa o plugin, o manual ganhou uma referência de **[Personalizar com CSS](/modulos/personalizar-css/)**: a lista das **classes** e das **variáveis de estilo** que o formulário de inscrição e a página do evento deixam disponíveis. Com ela, quem sabe um pouco de CSS pode ajustar cores, fontes, cantos e espaçamentos pelo **CSS adicional** do tema — ou reaproveitar os elementos em conteúdos com design mais avançado — sem editar o plugin.

## Formulário mais claro e topo da página mais bonito
**v1.36.1–v1.37.0 · julho de 2026**

Vários acertos de usabilidade a partir do uso real:

- **Campos de "escolha" ocupam a linha inteira** — campos do tipo checkbox/opções não ficam mais espremidos ao lado dos campos de texto.
- **Inscrição individual mais enxuta** — quando a inscrição é "só para mim", os botões **"+ Adicionar participante"** e **"× Remover"** somem (não faz sentido ter mais de um). No grupo, o último participante também não pode ser removido.
- **Topo (Hero) sem imagem** — se o evento não tem imagem, o topo aparece no modo **"só texto"** (nome, data e local sobre as cores do evento), em vez de esticar o logo.
- **Toque mais fácil no celular** — checkboxes e botões um pouco maiores.

## Galeria de modelos de página + modo claro/escuro
**v1.36.0 · julho de 2026**

A página do evento (layout "Página do plugin") ganhou uma **galeria de modelos**: agora são **6 estilos com personalidades diferentes** — Moderno, Compacto, **Vibrante** (lúdico), **Clássico** (formal, com serifa), **Minimalista** e **Energia** (esportivo). Cada um tem tipografia, formas e acento próprios, e **as cores continuam vindo do seu evento**. Você escolhe pela galeria, vendo uma prévia de cada um.

E há um novo controle de **Esquema de cor** — **Claro, Escuro** ou **Sistema** (que segue o aparelho de cada visitante) — que vale para todos os modelos, com bom contraste nos dois modos. Veja **[Editor de evento](/modulos/editor-evento/)**.

## Escolha como o topo da página do evento aparece (Hero)
**v1.35.0 · julho de 2026**

Agora você decide, em cada evento, **como o topo (Hero) da página aparece** — na aba **Página** do editor:

- **Só imagem** — mostra a **arte inteira, sem cortar** e sem texto por cima. Perfeito quando a sua arte de divulgação **já traz nome, data e local** — ela aparece legível, inclusive no celular.
- **Imagem + texto** — a arte vira fundo e o plugin escreve título, data e local por cima, com contraste.
- **Só texto** — sem imagem, sobre as cores do evento.

Há também um campo **Imagem do Hero** para escolher a arte do topo. Veja **[Editor de evento](/modulos/editor-evento/)**.

## Campo de múltipla escolha e correções no formulário
**v1.34.0 · julho de 2026**

O campo **checkbox** do formulário agora pode ter **opções** — vira uma **múltipla escolha** (o participante marca mais de uma, ex.: restrições alimentares). E as opções de **escolha** (radio) e das caixas agora ficam **cada uma em sua linha**, sem se encavalar. Veja **[Editor de evento](/modulos/editor-evento/)**.

## E-mails mais limpos na inscrição
**v1.33.0 · julho de 2026**

Ao se inscrever num evento, o participante passa a receber **apenas os e-mails do V3REvent** (confirmação, recibo, credencial) — os e-mails genéricos de "pedido" do WooCommerce deixam de ser enviados nas inscrições, para não confundir.

## API e Webhooks para integrar com outros sistemas
**v1.31.0–v1.32.0 · julho de 2026**

O V3REvent ganhou uma nova tela **Shortcodes e API** com tudo para conectar seus eventos a outros sistemas (como o **n8n**):

- **API de leitura** — gere **chaves de API** (com escopo por evento) para um sistema externo ler eventos, inscrições e inscritos.
- **Webhooks** — o V3REvent **avisa automaticamente** um serviço externo quando algo acontece: inscrição confirmada, check-in, credencial emitida, evento publicado e mais (9 gatilhos). Com botão **Testar**, log de entregas e assinatura de segurança.
- **Shortcodes** — a lista dos shortcodes do plugin, com botão copiar, num lugar só.

Veja **[Shortcodes e API](/modulos/shortcodes-e-api/)**.

## Anexar documentos ao evento (regulamento, kit…)
**v1.30.0 · julho de 2026**

Agora dá para **anexar documentos ao evento** — regulamento, kit do participante, o que precisar — na nova aba **Documentos** do editor. Cada arquivo recebe um **título** e vira um **link de download** na página do evento. Você **reordena** os documentos e escolhe **onde a lista aparece** (antes ou depois da inscrição, após as informações, ou não exibir). Também há o shortcode `[v3revent_documents]` para colocar a lista em qualquer página. Veja **[Editor de evento](/modulos/editor-evento/)**.

## Descrição do evento com editor de formatação
**v1.29.0 · julho de 2026**

A **descrição do evento** (aba Detalhes do editor) agora tem um **editor com formatação** — o mesmo editor do WordPress. Dá para usar **negrito**, listas, títulos, links e citações, alternar entre **Visual** e **Texto (HTML)**, e **inserir imagens** pelo botão **Adicionar mídia**. Tudo isso aparece na página pública do evento. Veja **[Editor de evento](/modulos/editor-evento/)**.

## "Responsável pela inscrição" agora é opcional
**v1.28.0 · julho de 2026**

Antes, o formulário sempre pedia os **Dados do Responsável pela Inscrição** — o que só fazia sentido quando alguém inscrevia um grupo. Agora cada evento tem um **Tipo de inscrição** (aba Detalhes do editor):

- **O participante escolhe** (novo padrão) — o formulário pergunta **"Para quem é esta inscrição?"** e só mostra o responsável quando é para um grupo.
- **Somente individual** — esconde o responsável; o contato é o próprio participante.
- **Sempre em grupo** — mantém o responsável como passo obrigatório (comportamento anterior).

Assim, quem se inscreve sozinho não vê mais um campo que não usava. Veja **[Formulário público](/modulos/formulario-publico/)** e **[Editor de evento](/modulos/editor-evento/)**.

## Botão "Ver página" do evento
**v1.27.0 · julho de 2026**

Ficou muito mais fácil **encontrar e abrir a página pública** de um evento. Agora existe o botão **Ver página** em dois lugares: na tela **Eventos** (na linha de cada evento) e no topo do **editor** do evento. Um clique abre a página pública em uma nova aba — o link que você divulga.

Enquanto o evento está em **rascunho**, o botão vira **Pré-visualizar**: você confere como a página vai ficar antes de publicar, sem que o público veja.

{: .note }
> Lembrete útil: a página do evento é publicada **automaticamente** e **não** aparece no menu **Páginas** do WordPress — o evento é gerido pela tela **V3REvent → Eventos**. Veja **[Página do evento](/modulos/pagina-do-evento/)**.

## Preço por modalidade mais fácil e cores herdadas
**v1.26.0 · julho de 2026**

Três melhorias de usabilidade no **editor de evento**, a partir de sugestões de quem usa o plugin:

- **Preço por modalidade** virou uma opção direta no **Modo de preço** (aba Tabela de Preços), ao lado de "Por quantidade" e "Por lote". Antes era preciso descobrir um campo escondido — agora é só escolher **Por modalidade de inscrição** e apontar o campo do formulário (ex.: "Modalidade": Jovem / Chefe / Equipe), com uma tabela de preços por opção.
- **Cores dos eventos herdam as globais.** As cores definidas em **Configurações → Aparência** agora são o **padrão automático** de todo evento — você só personaliza um evento se quiser. Mudar a cor global atualiza todos os eventos que seguem o padrão.
- **Abas do editor** deixam de quebrar em duas linhas: quando são muitas, a barra **rola na horizontal**, sem esconder nenhuma.

Veja **[Editor de evento](/modulos/editor-evento/)**.

## Preço por lote (data) e data limite de inscrições
**v1.25.0 · julho de 2026**

A **Tabela de Preços** ganhou um **modo de preço**: além do "Por quantidade" (desconto por grupo), agora há **"Por lote (data)"**. Você cadastra lotes com **janela de data** e **preço** — ex.: 1º lote R$ 100, 2º R$ 110, 3º R$ 120 — e o sistema cobra automaticamente o **lote ativo na data da inscrição**, sem precisar trocar o preço na virada. Perfeito para **corridas** e eventos com lotes. Também entrou, na aba **Detalhes**, uma **Data limite de inscrições** (opcional) que **fecha o formulário automaticamente** na data marcada. Veja **[Editor de evento](/modulos/editor-evento/)**.

## Relatório do evento em PDF
**v1.24.0 · julho de 2026**

Ao fechar um evento, você agora emite um **relatório consolidado em PDF**, escolhendo **quais seções incluir e em que ordem**: dados da organização, dados gerais, patrocinadores, programação, inscritos e presença, **valores (previsto × arrecadado)**, avaliação, lições aprendidas, texto livre e equipe. Uma nova aba **Relatório** no editor guarda a configuração; o PDF é **gerado na hora** com os dados atuais e **baixado no painel** (documento interno, sem link público). Também dá para gerá-lo pelo ícone de relatório na lista de eventos. Veja **[No dia e depois](/guia-do-gestor/no-dia-e-depois/)**.

## Patrocinadores do evento
**v1.23.0 · julho de 2026**

Cada evento ganhou uma aba **Patrocinadores** (opcional) para cadastrar patrocinadores e apoiadores: nome, CNPJ/CPF, **logomarca**, site, tipo (patrocínio, apoio, realização, parceria), **valor** (dinheiro ou permuta, com situação previsto/confirmado/recebido) e as **contrapartidas** negociadas. Na **página pública** do evento, os **logos aparecem agrupados por tipo**; os dados financeiros e as contrapartidas ficam só no seu controle. Tudo isso também alimenta o novo **Relatório** do evento. Veja **[Editor de evento](/modulos/editor-evento/)**.

## Certificado de participação
**v1.22.0 · julho de 2026**

Chegou o **certificado de participação**: uma nova aba **Certificado** no editor, com modelos prontos (Clássico e Moderno) na logo e nas cores do evento, carga horária opcional e **envio por e-mail** aos elegíveis. Quem é elegível depende da **modalidade** do evento — em **presencial**, quem fez **check-in**; em **virtual**, quem tem inscrição confirmada. Cada certificado tem um **link público de verificação** e versão em PDF. Veja **[Documentos](/modulos/documentos/)**.

## Ações da lista de eventos mais limpas
**v1.21.0 · julho de 2026**

Na tela **Eventos**, os botões **Editar** e **Duplicar** viraram **ícones** (lápis e cópia) com uma **dica ao passar o mouse**, deixando a lista mais enxuta e fácil de ler. O comportamento é o mesmo — e agora também totalmente acessível pelo teclado. Veja **[Eventos](/modulos/eventos/)**.

## Avaliação do evento
**v1.20.0 · julho de 2026**

Chegou a **pesquisa de avaliação** do evento — uma nova aba **Avaliação** no editor, com quatro áreas:

- **Perguntas** — monte a pesquisa com tipos prontos: **nota (1–5)**, **NPS (0–10)**, escolha única, múltipla escolha e texto livre.
- **Convites** — envie o convite da pesquisa por e-mail **aos presentes** (com a opção de mandar só para quem ainda não respondeu).
- **Resultados** — veja os números **de forma anônima**: score NPS, médias das notas, distribuição das escolhas, comentários e a taxa de resposta.
- **Retrospectiva** — registre as suas **lições aprendidas** como coordenador.

A pesquisa é **anônima e respondida pelos participantes que fizeram check-in**: cada um recebe um link próprio, responde sem precisar de login, e a resposta **não fica vinculada à pessoa** — só o fato de ter respondido é registrado (para não duplicar e calcular a taxa de resposta). Veja **[No dia e depois](/guia-do-gestor/no-dia-e-depois/)**.

## Exportar a lista de presentes
**v1.19.0 · julho de 2026** *(coluna de horário de check-in a partir da v1.20.1)*

Na tela **Relatórios**, além de **Exportar todos**, agora há **Exportar presentes** — um arquivo (CSV, XLSX ou PDF) só com quem realmente compareceu (fez check-in). A partir da **v1.20.1**, esse arquivo traz também uma coluna **Check-in** com o **horário** de presença de cada pessoa. Ideal para enviar a pesquisa de avaliação a quem participou, emitir declarações ou ações de fidelização. Veja **[Relatórios](/modulos/relatorios/)**.

## Ordem das abas do editor mais natural
**v1.18.0 · julho de 2026**

As abas do editor de evento foram reordenadas para acompanhar o fluxo real de trabalho: **Detalhes → Programação → Campos do Formulário → Tabela de Preços → Aparência → Página → Credencial → WooCommerce → Equipe**.

## Check-in por QR e credenciamento
**v1.16.0 · julho de 2026**

Chegou o **check-in**: escaneie o QR da credencial (pela tela **Check-in** no painel ou pela própria página da credencial no celular) e a presença é marcada na hora, com retorno colorido — verde para confirmado, amarelo para quem já havia entrado, vermelho para código inválido. É reversível e não duplica presença. Os **Relatórios** ganharam a coluna de **Presença**. Veja **[Check-in](/modulos/checkin/)**.

## Credencial com QR e networking consentido
**v1.14.0 · julho de 2026**

Cada participante confirmado ganha uma **credencial** (crachá) com a logo e as cores do evento, em três modelos. O **QR** carrega, por padrão, apenas o código de validação; com o consentimento de **networking** do participante, passa a carregar um **cartão de contato (vCard)** para facilitar conexões — sempre preservando o código para o check-in. Dá para enviar a credencial automaticamente e gerar em lote para impressão. Veja **[Documentos](/modulos/documentos/)**.

## Suporte ao CNPJ alfanumérico
**v1.15.0 · julho de 2026**

O perfil da organização passou a aceitar o **novo CNPJ alfanumérico** da Receita Federal (ex.: `12.ABC.345/01DE-35`), com validação do dígito verificador. O CNPJ numérico continua funcionando exatamente como antes.

## Recibo automático em PDF
**v1.13.0 · julho de 2026**

Ao concluir o pedido, o responsável (pagador) recebe por e-mail um **recibo em PDF** na identidade do evento e da organização, com um **link permanente** para reemissão a qualquer momento. O recibo é um comprovante de pagamento — não substitui a nota fiscal.

## Páginas de evento por temas e compartilhamento
**v1.11.0 · julho de 2026**

Um **motor de páginas de evento** permite publicar o evento como uma **página inteira temática** (hero, informações, programação e formulário de inscrição), com botões de **compartilhamento** em redes sociais e no WhatsApp. Veja **[Página do evento](/modulos/pagina-do-evento/)**.

## Programação e galeria de imagens
**v1.9.0 – v1.10.0 · julho de 2026**

Cadastre a **programação** do evento (sessões, horários, palestrantes, trilhas) e uma **galeria de imagens** — ambos aparecem na página pública e nos blocos disponíveis.

## Precificação por modalidade
**v1.8.0 · julho de 2026**

Além do preço por faixa de quantidade, o evento pode ter um **campo de preço** (ex.: "Modalidade") em que **cada opção tem a sua própria tabela de faixas**. O total é a soma por modalidade.

## RBAC: três papéis de acesso
**v1.0.0 · julho de 2026**

O acesso passou a ser controlado por **três papéis** — Administrador da Organização, Coordenador de Eventos e Equipe de Evento —, cada um com o alcance certo. Você designa coordenadores e equipe **por evento**, na aba **Equipe**. Veja **[Primeiros passos](/primeiros-passos/)**.

## Feedback e manual no cabeçalho
**v0.8.0 · julho de 2026**

No cabeçalho de qualquer tela há dois botões: **Manual do Usuário** (abre este manual) e **Enviar Feedback**, para mandar sugestões, dúvidas ou relatos de bug à equipe V3RTECH sem sair do plugin — com um diagnóstico técnico automático que acelera o suporte, e sem expor seus dados sensíveis. Veja **[Ajuda e Feedback](/modulos/ajuda-e-feedback/)**.

---

## Recursos consolidados
*A base do V3REvent, presente desde as primeiras versões.*

### Eventos configuráveis por painel
Cada evento tem datas, local, capacidade, **faixas de preço**, **campos de formulário** (10 tipos), aparência (logo e cores) e produto no WooCommerce criado automaticamente ao publicar.

### Inscrição em lote com preço ao vivo
O responsável inscreve um grupo num único pedido, adiciona participantes à mão ou **importando uma planilha** (CSV/XLSX), e vê o **preço recalculado ao vivo** conforme a quantidade, com a faixa ativa em destaque.

### Pagamento pelo WooCommerce
A inscrição usa o carrinho, o checkout e os meios de pagamento do WooCommerce, com o preço sobrescrito pelas faixas do evento. Compatível com o armazenamento moderno de pedidos (HPOS).

### Comunicação automática
Cada participante recebe um e-mail de confirmação com o **código de inscrição**; o responsável recebe um relatório. Os e-mails são enviados em fila, para não travar o checkout em listas grandes.

### Relatórios e exportação
Painel com indicadores e gráficos, lista de inscrições com filtros e mudança de status, e relatórios por evento com colunas dinâmicas. Exportação em **CSV, XLSX e PDF**.

### LGPD por padrão
Consentimento obrigatório no formulário, **retenção** configurável com expurgo automático, e ferramentas para atender aos **direitos do titular** (exportar, excluir/anonimizar).
