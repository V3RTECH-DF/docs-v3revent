---
title: Shortcodes e API
parent: Módulos
nav_order: 12
---

# Shortcodes e API

A tela **Shortcodes e API** (menu do V3REvent) reúne três recursos para você exibir conteúdo em páginas e **integrar o V3REvent com outros sistemas** (como o [n8n](https://n8n.io)). Ela tem quatro abas.

## Shortcodes

A lista dos **shortcodes** do plugin, cada um com um botão **Copiar**. Cole-os em qualquer página ou post (pelo bloco “Shortcode” do editor) para exibir partes do evento — formulário de inscrição, programação, galeria, documentos, patrocinadores e compartilhamento.

![Aba Shortcodes](/assets/screenshots/api-shortcodes.png)

## Chaves de API

Para um sistema externo **ler** dados do V3REvent (eventos, inscrições, inscritos), ele precisa de uma **chave de API**.

1. Clique em **Nova chave**, dê um nome (ex.: “Integração n8n”) e escolha o **escopo**: todos os eventos ou apenas eventos selecionados.
2. A chave (`v3re_…`) é **mostrada uma única vez** — copie e guarde com segurança. Se perder, gere outra.
3. Use a chave no sistema externo enviando o cabeçalho **`X-V3REvent-Api-Key`** em cada requisição.

Você pode **revogar** uma chave a qualquer momento — a integração que a usa para de funcionar na hora. A coluna “último uso” ajuda a identificar chaves esquecidas.

![Aba Chaves de API](/assets/screenshots/api-chaves.png)

{: .note }
> A API de **inscritos** devolve dados pessoais (nome, e-mail, CPF), como no export. A sua organização é a responsável por esses dados; a chave é o controle de acesso. Crie chaves com o **menor escopo** necessário e revogue as que não usa.

## API (referência)

Mostra a **URL base** da API, o cabeçalho de autenticação e a lista de **endpoints** disponíveis (ler eventos, inscrições, inscritos, estatísticas e avaliação), com um exemplo pronto de requisição. É a documentação viva — reflete exatamente o que o plugin oferece.

## Webhooks

Enquanto a API é o sistema externo **puxando** dados, os **webhooks** são o V3REvent **empurrando** eventos assim que eles acontecem — ideal para automações no n8n.

1. Clique em **Novo webhook**, informe a **URL de destino** (precisa ser **`https://`**) e marque os **gatilhos** que quer receber:
   - **Evento** criado / publicado / cancelado;
   - **Inscrições** abertas / encerradas;
   - **Inscrição** confirmada / cancelada;
   - **Check-in** realizado;
   - **Credencial** emitida.
2. Use **Testar** para enviar um sinal de teste e conferir se o destino responde. O painel mostra o **log das últimas entregas** (sucesso/falha e horário).
3. Pode **ativar/desativar** ou **remover** um webhook quando quiser.

![Aba Webhooks — novo webhook](/assets/screenshots/api-webhooks.png)

Cada entrega é um `POST` com o corpo em JSON e um cabeçalho **`X-V3REvent-Signature`** (assinatura HMAC). No n8n, valide essa assinatura com o **segredo do webhook** para ter certeza de que a chamada veio mesmo do V3REvent. Entregas que falham são **repetidas automaticamente** algumas vezes antes de desistir.

{: .tip }
> **Receita rápida no n8n:** crie um fluxo com um nó **Webhook** (método POST, HTTPS), copie a URL dele, cole aqui e marque o gatilho **“Inscrição confirmada”**. A cada nova inscrição paga, o n8n recebe os dados e você pode, por exemplo, adicionar uma linha numa planilha, criar um contato no CRM ou enviar uma mensagem — sem intervenção manual.
