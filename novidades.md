---
title: Novidades
nav_order: 7
---

# Novidades

O que mudou no V3REvent, em linguagem simples — **da mais recente para a mais antiga**. Cada novidade traz a **versão** em que foi introduzida, para você saber o que é realmente novo.

{: .note }
> A versão instalada aparece no cabeçalho do painel do V3REvent (ex.: `v1.32.0`). Compare com a lista abaixo para ver o que você já tem.

---

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
