---
title: Perguntas Frequentes
nav_order: 6
---

# Perguntas Frequentes

## Começando

<details markdown="1">
<summary>Onde encontro o V3REvent depois de instalar?</summary>

No menu lateral do painel do WordPress, procure o item **V3REvent**. Ele reúne o
Painel, Eventos, Inscrições, Relatórios, Check-in e Configurações. Veja
**[Primeiros passos](/primeiros-passos/)**.
</details>

<details markdown="1">
<summary>Criei o evento, mas não encontro a página dele. Onde ela fica?</summary>

A página do evento é **criada automaticamente** quando você **publica** o evento — no endereço `.../evento/nome-do-evento/`. Você **não precisa criá-la** nem colar shortcode.

Ela **não aparece** no menu **Páginas** do WordPress porque o evento é um conteúdo próprio do V3REvent (gerido em **V3REvent → Eventos**), e não uma "Página" comum — isso é o esperado. Para abrir a página, use o botão **Ver página**: na lista de **Eventos**, na linha do evento, ou no topo do **editor** do evento. Se o evento ainda está em **rascunho**, o botão vira **Pré-visualizar** (só você vê). Detalhes em **[Página do evento](/modulos/pagina-do-evento/)**.
</details>

<details markdown="1">
<summary>Preciso do WooCommerce?</summary>

Sim. O V3REvent usa o **WooCommerce** para o carrinho, o checkout e o pagamento
das inscrições. Ele precisa estar instalado e ativo. Eventos **gratuitos**
funcionam: basta configurar o preço como R$ 0 — o pedido passa pelo WooCommerce
mesmo assim.
</details>

<details markdown="1">
<summary>Preciso de conta na nuvem ou mensalidade de plataforma?</summary>

Não. O V3REvent é um plugin que roda no **seu próprio WordPress**. Os dados ficam
no seu servidor e você trabalha inteiramente dentro do `wp-admin`.
</details>

<details markdown="1">
<summary>Qual é a primeira coisa que devo configurar?</summary>

O **perfil da organização** (V3REvent → Configurações → Organização): nome, CNPJ,
endereço, contato e logo. Ele alimenta recibos, credenciais e e-mails de todos os
eventos. Passo a passo em **[Primeiros passos](/primeiros-passos/)**.
</details>

## Inscrições e preços

<details markdown="1">
<summary>Meu evento é individual — como tiro o campo "Responsável pela inscrição"?</summary>

No editor do evento, aba **Detalhes**, use o **Tipo de inscrição**. Escolha **"Somente individual"** para esconder de vez a seção do responsável, ou **"O participante escolhe"** (padrão) para que o formulário pergunte "Para quem é esta inscrição?" e só mostre o responsável quando for para um grupo. Em inscrições individuais, o contato passa a ser o próprio participante (nome/e-mail do checkout). Detalhes em **[Formulário público](/modulos/formulario-publico/)**.
</details>

<details markdown="1">
<summary>Como funciona o preço por faixa de quantidade?</summary>

Ligue **Desconto por quantidade** na aba **Preços** do evento: cada faixa tem uma
quantidade mínima, máxima e um preço por inscrito. Quanto maior o grupo, menor o
valor unitário. A faixa é destravada pelo **total de inscritos do pedido** (mesmo
misturando modalidades), e o formulário mostra a faixa ativa em destaque e recalcula
o total ao vivo. Veja **[Criar um evento](/criar-evento/)**.
</details>

<details markdown="1">
<summary>Posso ter preços diferentes por tipo de participante?</summary>

Sim. Ligue **Preço por modalidade** na aba **Preços**: designe um campo de seleção
(ex.: "Estudante" / "Profissional") como campo de preço, e dê a **cada opção sua
própria tabela**. O total é a soma por modalidade — e você ainda pode **combinar**
com lotes por data e desconto por quantidade. Veja
**[Editor de evento → Preços](/modulos/editor-evento/)**.
</details>

<details markdown="1">
<summary>Como o responsável inscreve muita gente sem digitar um a um?</summary>

Pelo botão de **importar planilha** no formulário: ele baixa um modelo, preenche em
CSV/XLSX e importa — os cards de participante são preenchidos automaticamente. Veja
**[Formulário público](/modulos/formulario-publico/)**.
</details>

<details markdown="1">
<summary>O que acontece quando o evento lota?</summary>

O formulário **não bloqueia**: avisa que a inscrição entrará como **excedente** e
deixa prosseguir. Na lista de inscrições, os excedentes ficam sinalizados. Para
fechar de vez, desligue **Inscrições abertas** na aba Detalhes do evento.
</details>

## Pagamento e documentos

<details markdown="1">
<summary>O V3REvent recebe o dinheiro das inscrições?</summary>

Não. Quem processa o pagamento é o **WooCommerce** com o gateway que você
configurou. A V3RTECH não recebe, não intermedia e não retém valores. A relação de
compra é entre você (organizador) e o inscrito.
</details>

<details markdown="1">
<summary>O recibo do V3REvent é nota fiscal?</summary>

Não. O recibo é um **comprovante de pagamento** com a identidade do evento e os
dados da organização. A emissão de **nota fiscal**, quando exigível, é uma
obrigação sua, feita à parte. Veja **[Documentos](/modulos/documentos/)**.
</details>

<details markdown="1">
<summary>O participante recebe alguma confirmação?</summary>

Sim. Ao concluir o pedido, cada participante recebe um e-mail de confirmação com o
seu **código de inscrição** único, e o responsável recebe um relatório e o
**recibo em PDF**. Se você habilitar, a **credencial** também é enviada
automaticamente.
</details>

## Credencial e check-in

<details markdown="1">
<summary>O que é o QR da credencial e o "networking consentido"?</summary>

Cada credencial tem um **QR**. Por padrão, ele aponta só para a página de validação
(usada no check-in). Se o participante **consentir com o networking** (uma opção no
formulário), o QR passa a carregar um **cartão de contato (vCard)** com nome,
e-mail, telefone e empresa — mantendo o código para o check-in. Veja
**[Documentos](/modulos/documentos/)**.
</details>

<details markdown="1">
<summary>Como faço o check-in no dia do evento?</summary>

Pela tela **Check-in** (leitor de QR por câmera ou entrada manual do código) ou
abrindo a credencial pelo celular, onde a equipe logada vê um botão de **Confirmar
presença**. O check-in é reversível e não duplica presença. Quem faz é a **Equipe
de Evento**. Veja **[Check-in](/modulos/checkin/)**.
</details>

<details markdown="1">
<summary>Um voluntário pode fazer só o credenciamento, sem acesso ao resto?</summary>

Sim. Adicione-o como **Equipe de Evento** na aba **Equipe** daquele evento. Ele
poderá acompanhar inscrições e fazer check-in, mas não alterará a configuração do
evento nem verá outros eventos ou as Configurações globais.
</details>

## Pós-evento: certificado, avaliação e relatório

<details markdown="1">
<summary>Quem recebe o certificado de participação?</summary>

Depende da **modalidade** do evento (aba Detalhes): em evento **presencial**, é
elegível quem fez **check-in**; em **virtual**, quem tem a inscrição confirmada.
Você ativa a emissão, escolhe o modelo e a carga horária na aba **Certificado** e
envia por e-mail aos elegíveis. Cada certificado tem um **link público de
verificação**. Veja **[Documentos](/modulos/documentos/)**.
</details>

<details markdown="1">
<summary>Os valores e as contrapartidas dos patrocinadores aparecem para o público?</summary>

Não. Na **página pública** do evento aparecem apenas o **logo, o nome e o tipo** do
patrocinador (agrupados por tipo). O **valor**, a **situação** e as
**contrapartidas** ficam só no painel e no **relatório do evento** — que é interno.
Veja **[Editor de evento](/modulos/editor-evento/)**.
</details>

<details markdown="1">
<summary>Qual a diferença entre a tela "Relatórios" e o "Relatório do evento"?</summary>

A tela **Relatórios** é de **acompanhamento e exportação** dos participantes
(indicadores, presença, CSV/XLSX/PDF). O **Relatório do evento** (aba **Relatório**
do editor) é um **PDF consolidado de fechamento**, com seções escolhíveis —
organização, patrocinadores, valores (previsto × arrecadado), avaliação, equipe e
mais. É gerado sob demanda e restrito ao painel.
</details>

<details markdown="1">
<summary>A pesquisa de avaliação é anônima?</summary>

Sim. Ela é liberada apenas para quem **fez check-in**, cada um responde por um link
próprio **sem login**, e a resposta **não fica vinculada à pessoa** — só o fato de
ter respondido é registrado (para não duplicar e calcular a taxa de resposta). Veja
**[No dia e depois](/guia-do-gestor/no-dia-e-depois/)**.
</details>

## Integração com outros sistemas

<details markdown="1">
<summary>Como integro o V3REvent com o n8n ou outro sistema?</summary>

Pela tela **Shortcodes e API**. Há dois caminhos: uma **API de leitura** (o outro sistema
usa uma **chave de API** para consultar eventos, inscrições e inscritos) e **webhooks** (o
V3REvent **avisa** o outro sistema quando algo acontece — inscrição confirmada, check-in
etc.). Passo a passo em **[Shortcodes e API](/modulos/shortcodes-e-api/)**.
</details>

## Dados e privacidade

<details markdown="1">
<summary>De quem é a responsabilidade pelos dados dos inscritos?</summary>

Sua. Ao coletar dados de participantes, **você é o controlador** pela LGPD. O
V3REvent oferece as ferramentas (consentimento no formulário, retenção com expurgo
automático, exportação e exclusão), mas a base legal e a política de privacidade
são sua responsabilidade. Veja **[Política de Privacidade](/legal/privacidade/)**.
</details>

<details markdown="1">
<summary>Por quanto tempo os dados ficam guardados?</summary>

Pelo prazo de **retenção** que você definir em Configurações → Avançado. Passada a
janela, os dados de inscritos de eventos encerrados são **expurgados
automaticamente**. Você também pode excluir uma inscrição manualmente a qualquer
momento.
</details>

<details markdown="1">
<summary>Como envio uma sugestão ou reporto um problema?</summary>

Use o botão **Enviar Feedback** no canto superior direito de qualquer tela do
V3REvent. Escolha o tipo (Sugestão, Dúvida, Bug, Depoimento ou Outros), escreva sua
mensagem e envie — um diagnóstico técnico (sem dados pessoais) vai junto para
acelerar o suporte, e você recebe uma cópia por e-mail. Veja
**[Ajuda e Feedback](/modulos/ajuda-e-feedback/)**.
</details>
