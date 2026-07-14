---
title: Criar um evento de ponta a ponta
nav_order: 3
---

# Criar um evento de ponta a ponta

Este é o caminho completo, na ordem natural do trabalho: do rascunho do evento à primeira inscrição paga, passando por preços, campos do formulário, aparência e publicação. Cada etapa tem uma página de referência com mais detalhes — mas seguir esta sequência já coloca o seu evento no ar.

{: .note }
> **Antes de começar**
>
> Tenha o **[perfil da organização](/primeiros-passos/)** preenchido. Ele alimenta os documentos (recibo, credencial) e os e-mails do evento.

## Passo 1 — Criar o evento

1. No menu, abra **V3REvent → Eventos**.
2. Clique em **Novo Evento**. O plugin cria um evento em **rascunho** e abre o editor.

O editor é organizado em abas, na ordem em que você normalmente as preenche: **Detalhes → Programação → Campos do Formulário → Tabela de Preços → Aparência → Página → Credencial → WooCommerce → Equipe**.

![Editor de evento — aba Detalhes](/assets/screenshots/evento-editor-detalhes.png)

## Passo 2 — Detalhes do evento

Na aba **Detalhes**, informe:

- **Título** do evento;
- **Data e hora de início** (obrigatória) e **de término**;
- **Local** e, se houver, o **link do local** (mapa ou página);
- **Capacidade total** (0 = ilimitada);
- **Máximo de inscritos por pedido** (limita o tamanho de cada grupo);
- **Inscrições abertas** (liga/desliga o formulário);
- **Status** do evento.

{: .tip }
> **Capacidade e política de excedente**
>
> Ao atingir a capacidade, o formulário **não bloqueia** a inscrição: ele avisa que o grupo entrará como **excedente** e deixa prosseguir. Na lista de inscrições, os excedentes ficam sinalizados para você decidir. Isso evita perder um grupo grande por uma ou duas vagas — mas exige sua atenção ao encerrar as vendas.

## Passo 3 — Campos do formulário

Na aba **Campos do Formulário**, você define **quais dados coletar de cada participante**. Cada campo é um card com id, rótulo, tipo, obrigatoriedade, placeholder, opções e ordem (arraste para reordenar).

Tipos disponíveis: texto, e-mail, CPF, telefone, número, seleção (select), múltipla escolha (radio), caixas (checkbox), área de texto e data. O conjunto padrão já traz **nome, CPF, e-mail, organização e telefone**.

![Editor de evento — Campos do Formulário](/assets/screenshots/evento-editor-campos.png)

{: .important }
> **Colete só o necessário (minimização de dados)**
>
> Cada campo obrigatório é um dado pessoal de terceiro que você passa a guardar. Pela LGPD, peça apenas o que realmente vai usar. Precisa de CPF para emitir certificado? Mantenha. Não vai usar o telefone? Considere torná-lo opcional ou removê-lo.

## Passo 4 — Tabela de preços

Na aba **Tabela de Preços**, monte as **faixas por quantidade**: para cada faixa você define a quantidade mínima, a máxima (deixe a última em branco para "acima de") e o preço por inscrito, com um rótulo. Quanto maior o grupo, menor o valor unitário.

![Editor de evento — Tabela de Preços](/assets/screenshots/evento-editor-precos.png)

Se o seu evento tem **modalidades com preços diferentes** (ex.: "Estudante" e "Profissional"), você pode designar um **campo de preço** (um select do formulário) em que **cada opção tem a sua própria tabela de faixas**. O total é a soma por modalidade, e a faixa é calculada pela contagem de cada uma.

{: .tip }
> **Ancoragem que incentiva o grupo**
>
> Faixas bem desenhadas transformam "vou levar 3" em "vamos fechar 10". Deixe o salto de preço entre faixas visível e convidativo — o formulário mostra a faixa ativa em destaque e recalcula o total ao vivo conforme o responsável adiciona gente.

## Passo 5 — Aparência

Na aba **Aparência**, dê identidade ao evento: **logo** (pela Biblioteca de Mídia), **cor primária**, **cor secundária** e **fonte**. Essas escolhas valem para o formulário público, a página do evento, os e-mails, o recibo e a credencial daquele evento — sobrepondo o padrão global.

![Editor de evento — Aparência](/assets/screenshots/evento-editor-aparencia.png)

## Passo 6 — Programação e página (opcional, mas recomendado)

- Na aba **Programação**, cadastre as **sessões** do evento (dia, horário, título, palestrante, trilha, local). Elas aparecem na página pública e ajudam o inscrito a se planejar.
- Na aba **Página**, escolha o **layout** e o **tema visual** da página pública do evento (hero, informações, programação e o formulário de inscrição, tudo numa página inteira do plugin).

Veja **[Página do evento](/modulos/pagina-do-evento/)** para os temas disponíveis.

## Passo 7 — Credencial (opcional)

Na aba **Credencial**, escolha um dos **modelos de crachá** (com a logo e as cores do evento), decida se a credencial é **enviada automaticamente** por e-mail a cada inscrito e configure o **QR**. Por padrão, o QR carrega apenas o código de validação; com o consentimento de **networking** do participante, ele carrega um **cartão de contato (vCard)** para facilitar conexões no evento. Veja **[Documentos: recibo e credencial](/modulos/documentos/)**.

## Passo 8 — Publicar

Ao **publicar** o evento (mudando o status de rascunho para publicado), o V3REvent **cria automaticamente um produto no WooCommerce** vinculado ao evento. Você não precisa mexer nesse produto — ele é oculto do catálogo e tem o preço controlado pelas suas faixas.

Na aba **WooCommerce**, você encontra o produto vinculado e o **shortcode** do formulário — por exemplo `[v3revent_registration event_id="123"]` — com um botão para copiar. Use-o para inserir o formulário em qualquer página.

![Editor de evento — WooCommerce e shortcode](/assets/screenshots/evento-editor-woocommerce.png)

## Passo 9 — Divulgar e receber inscrições

Há três formas de expor o formulário:

- **Página single do evento** — o formulário é injetado automaticamente ao fim do conteúdo do evento;
- **Shortcode** `[v3revent_registration]` — em qualquer página ou post;
- **Página do evento por template** — se você ativou um layout na aba Página.

O responsável então preenche os dados, adiciona os participantes (à mão ou **importando uma planilha**), vê o preço ao vivo e finaliza pelo checkout do WooCommerce. Veja como fica em **[Formulário público de inscrição](/modulos/formulario-publico/)**.

![Formulário público de inscrição](/assets/screenshots/form-publico.png)

## Passo 10 — O que acontece após o pagamento

Quando o pedido é concluído no WooCommerce, o V3REvent automaticamente:

1. **Registra a inscrição** e cada participante no banco, com um **código de inscrição** único (`XXXX-XXXX`);
2. Envia a **cada participante** um e-mail de confirmação com o seu código;
3. Envia ao **responsável** um relatório com a lista de inscritos e o **recibo em PDF**;
4. Emite e envia a **credencial**, se você habilitou o envio automático.

Daí em diante, o trabalho é de acompanhamento: **[Inscrições](/modulos/inscricoes/)**, **[Relatórios](/modulos/relatorios/)** e, no dia, **[Check-in](/modulos/checkin/)**.

{: .note }
> **Quer ver tudo funcionando antes de divulgar?**
>
> Faça uma **inscrição de teste** com dados fictícios e um valor baixo. Confira o e-mail de confirmação, o recibo e a credencial, e veja a inscrição aparecer em Inscrições e Relatórios. É a melhor forma de validar campos, preços e comunicação antes de abrir ao público.
