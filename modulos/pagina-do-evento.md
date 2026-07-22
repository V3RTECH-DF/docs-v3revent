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

Na aba **Página** do editor, você escolhe o **layout** e o **tema visual**. Os temas variam a estrutura da página (por exemplo, um mais claro e amplo com hero de destaque, outro mais compacto e escuro), sempre respeitando a **logo e as cores do evento**.

## As seções da página

Conforme o tema, a página pode incluir:

- **Hero** — título, data e local em destaque;
- **Informações** — detalhes do evento;
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
