---
title: Página do evento
parent: Módulos
nav_order: 9
---

# Página do evento

O V3REvent pode publicar o evento como uma **página inteira temática**, reunindo tudo o que o visitante precisa: apresentação, informações, programação, galeria e o formulário de inscrição — sem depender do layout do seu tema.

![Página pública do evento com hero, informações e programação](/assets/screenshots/pagina-evento.png)

## Onde fica a página do evento?

Assim que você **publica** um evento, ele **já tem uma página pública própria** — no endereço `.../evento/nome-do-evento/`. Você **não precisa criar uma página** no WordPress nem colar nada: o V3REvent cuida disso sozinho.

{: .note }
> **Por que a página não aparece em "Páginas" do WordPress?**
>
> Porque o evento **não é** uma "Página" comum do WordPress — é um tipo de conteúdo próprio do V3REvent, gerido pela tela **V3REvent → Eventos**. Por isso ele não aparece na lista de **Páginas**, e isso é o esperado. Para abrir, editar ou compartilhar a página, use sempre a tela **Eventos**.

Para abrir a página, use o botão **Ver página**:

- Na tela **[Eventos](/modulos/eventos/)**, na linha do evento, clique no ícone **Ver página** (dica ao passar o mouse).
- Ou, dentro do **[editor do evento](/modulos/editor-evento/)**, clique em **Ver página** no topo (ao lado de "Voltar").

Nos dois casos a página abre em uma nova aba. É esse o link que você divulga para o público.

### Ainda em rascunho? Use "Pré-visualizar"

Enquanto o evento está em **rascunho** (ainda não publicado), o botão vira **Pré-visualizar**: ele mostra como a página vai ficar, só para você (o público ainda não vê o evento). Assim você confere tudo antes de publicar. Depois de publicado, o botão passa a ser **Ver página** e o endereço fica público.

![Botão "Pré-visualizar" no topo do editor de um evento em rascunho](/assets/screenshots/evento-previsualizar.png)

## Escolhendo o layout e o tema

Na aba **Página** do editor, você escolhe o **layout** e o **modelo visual**.

O **layout** define como a página se encaixa no seu site:

- **Tema do site** — o evento aparece **dentro do seu site**, com o **cabeçalho e o rodapé do tema** ao redor.
- **Página do plugin** — o evento aparece em **tela cheia** (*hotsite* / *onepage*), **sem o cabeçalho e o rodapé do tema**: só o conteúdo do evento, ocupando a tela inteira. É uma página de divulgação focada, que abre limpa e vai direto à inscrição.

{: .note }
> **A partir da v1.39.0**, o layout **Página do plugin** é **tela cheia, sem o cabeçalho e o rodapé do site**. Para manter o cabeçalho e o rodapé do seu tema ao redor do evento, use **Tema do site**.

Os **modelos** variam a personalidade visual da página (tipografia, formas, acento e espaçamento), sempre respeitando a **logo e as cores do evento**. Veja a galeria e os detalhes em **[Editor de evento → Página](/modulos/editor-evento/)**.

## As seções da página

Conforme o tema, a página pode incluir:

- **Hero** — título, data e local em destaque;
- **Aviso de inscrições** — cartão logo abaixo do topo quando as inscrições não estão abertas (veja abaixo);
- **Contagem regressiva** — contadores ao vivo para o início do evento e o fim das inscrições (opcional, veja abaixo);
- **Contato dos organizadores** — cartão "Fale com a organização" com os canais de atendimento (opcional, veja abaixo);
- **Informações** — **data e local em destaque**, centralizados em "pílulas" com ícone (calendário e localização), seguidos da descrição do evento também centralizada;
- **Programação** — as sessões cadastradas, agrupadas por dia, com trilhas em destaque;
- **Galeria** — imagens do evento;
- **Documentos** — regulamento, kit do participante e outros arquivos como links de download (a posição é escolhida na aba **[Documentos](/modulos/editor-evento/)** do editor);
- **Inscrição** — o formulário embutido;
- **Patrocinadores** — os logos dos patrocinadores e apoiadores, **agrupados por tipo** (patrocínio, apoio, realização…), cada um exibido sobre um **fundo branco fixo** e linkado ao site do patrocinador;
- **Compartilhar** — botões para WhatsApp, redes sociais e o compartilhamento nativo do celular.

![Seção de patrocinadores na página do evento](/assets/screenshots/pagina-evento-patrocinadores.png)

{: .note }
> Na página pública aparecem apenas o **logo, o nome e o tipo** do patrocinador. Valor, situação e contrapartidas ficam só no painel (aba **[Patrocinadores](/modulos/editor-evento/)** do editor).

{: .note }
> Cada logo de patrocinador é sempre exibido sobre um **fundo branco**, independentemente do tema escolhido ou do modo claro/escuro. Isso garante bom contraste até para logos transparentes ou feitas para fundo claro. Por isso você pode enviar as artes em **PNG com fundo transparente** — elas aparecem sobre o fundo branco padrão. (Patrocinador sem logo mostra o nome em texto escuro sobre o branco.)

{: .note }
> **A logo do evento** aparece na página **com destaque**, sobre um **cartão branco** (legível em tema claro ou escuro). Você escolhe **onde ela aparece** — no topo, abaixo do hero, junto das informações — ou **não mostrá-la** na página, e também o **tamanho** dela (Pequeno, Médio, Grande ou Personalizado), em **[Editor de evento → Aparência](/modulos/editor-evento/)**.

## Acessibilidade: tamanho do texto

No topo da página, o visitante encontra uma pequena barra **A− / A / A+** para **diminuir, restaurar ou aumentar** o tamanho do texto — uma ajuda para quem tem baixa visão ou prefere uma leitura mais confortável. A preferência fica **guardada no navegador** dele, valendo nas próximas visitas.

![Página do evento em tamanho normal (100%), com a barra de acessibilidade A− / A / A+ no topo](/assets/screenshots/pagina-acessibilidade-100.png)

Ao clicar em **A+**, o conteúdo é ampliado sem quebrar o layout:

![Mesma página com o texto ampliado após clicar em A+](/assets/screenshots/pagina-acessibilidade-ampliado.png)

O recurso vem **ligado por padrão** no layout **Página do plugin**. Se quiser, você o desliga por evento na aba **[Aparência](/modulos/editor-evento/)** do editor.

## Documentos na página

Quando você anexa documentos ao evento (regulamento, kit do participante…), eles aparecem em uma **grade** — vários por linha, preenchendo a largura — com o **título da seção** que você definiu (aqui, *"Documentos complementares"*). Cada item é um **link de download** com a extensão do arquivo em destaque.

![Seção de documentos na página do evento, em grade, com o título "Documentos complementares"](/assets/screenshots/pagina-evento-documentos.png)

O título da seção e a posição na página são definidos na aba **[Documentos](/modulos/editor-evento/)** do editor.

## Aviso de inscrições

Quando as inscrições **não estão abertas**, a página mostra um **cartão logo abaixo do topo** explicando o momento, em vez de simplesmente esconder o formulário:

- **Inscrições em breve** — antes da **data de abertura** (e mostra a data, se você a informou);
- **Inscrições encerradas** — depois da **data limite**;
- **Inscrições indisponíveis no momento** — quando o organizador fechou as inscrições manualmente.

O aviso é **automático**: você controla tudo pela aba **Detalhes** do editor (as datas de abertura e limite e o interruptor **Inscrições abertas**). Veja **[Editor de evento → Detalhes](/modulos/editor-evento/)**.

<!-- print pendente: pagina-aviso-inscricoes.png — página do evento com o cartão "Inscrições em breve" logo abaixo do topo, viewport desktop -->

## Contagem regressiva

Quando ligada na aba **Detalhes**, a página exibe um box com **contadores** que atualizam **ao vivo** (dias, horas, minutos e segundos): um para o **início do evento** e outro para o **fim das inscrições**. Cada contador só aparece se a sua data estiver preenchida e ainda for futura. Veja **[Editor de evento → Detalhes](/modulos/editor-evento/)**.

<!-- print pendente: pagina-contagem-regressiva.png — página do evento com o box de contagem regressiva, viewport desktop -->

## Contato dos organizadores

Quando ligado na aba **Detalhes**, aparece o cartão **"Fale com a organização"** com os canais que você preencheu — **e-mail**, **WhatsApp** e **telefone** (só os informados). O botão de WhatsApp abre a conversa direto. Veja **[Editor de evento → Detalhes](/modulos/editor-evento/)**.

<!-- print pendente: pagina-contato-organizadores.png — página do evento com o cartão "Fale com a organização", viewport desktop -->

## Montando à sua maneira (blocos e shortcodes)

Se você prefere usar o seu próprio tema ou o editor de blocos do WordPress, cada elemento também está disponível como **shortcode**, que você insere pelo bloco "Shortcode" do Gutenberg:

| Shortcode | O que insere |
|---|---|
| `[v3revent_registration]` | O formulário de inscrição. |
| `[v3revent_schedule]` | A programação do evento. |
| `[v3revent_gallery]` | A galeria de imagens. |
| `[v3revent_documents]` | Os documentos do evento (regulamento, kit…) como links de download. |
| `[v3revent_sponsors]` | Os patrocinadores, agrupados por tipo. |
| `[v3revent_share]` | Os botões de compartilhamento. |

{: .tip }
> **Compartilhar bem multiplica inscrições**
>
> Coloque a página no ar cedo e divulgue o link com os botões de compartilhamento. Uma página temática abre rápido, funciona bem no celular e transmite profissionalismo — o que aumenta a confiança de quem vai pagar a inscrição.
