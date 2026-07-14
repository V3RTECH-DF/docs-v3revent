---
title: Novidades
nav_order: 7
---

# Novidades

O que mudou no V3REvent, em linguagem simples — **da mais recente para a mais antiga**. Cada novidade traz a **versão** em que foi introduzida, para você saber o que é realmente novo.

{: .note }
> A versão instalada aparece no cabeçalho do painel do V3REvent (ex.: `v1.19.0`). Compare com a lista abaixo para ver o que você já tem.

---

## Exportar a lista de presentes
**v1.19.0 · julho de 2026**

Na tela **Relatórios**, além de **Exportar todos**, agora há **Exportar presentes** — um arquivo (CSV, XLSX ou PDF) só com quem realmente compareceu (fez check-in). Ideal para enviar a pesquisa de avaliação a quem participou, emitir declarações ou ações de fidelização. Veja **[Relatórios](/modulos/relatorios/)**.

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
