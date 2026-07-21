---
title: Chaves de API
parent: Shortcodes e API
grand_parent: Módulos
nav_order: 1
---

# Chaves de API

Para um sistema externo **ler** dados do V3REvent (eventos, inscrições, inscritos, totais), ele precisa se identificar com uma **chave de API**. A chave é como uma senha de acesso só de leitura: quem a tem consegue consultar os dados no escopo que você definir.

![Aba Chaves de API](/assets/screenshots/api-chaves.png)

## Criar uma chave

1. Na aba **Chaves de API**, clique em **Nova chave**.
2. Dê um **nome** que lembre onde ela será usada — ex.: "Integração n8n" ou "Dashboard financeiro".
3. Escolha o **escopo**:
   - **Todos os eventos** — a chave lê qualquer evento.
   - **Eventos selecionados** — a chave só enxerga os eventos que você marcar. Consultar um evento fora da lista devolve erro (`403`).
4. Confirme. A chave é gerada no formato **`v3re_…`** (ex.: `v3re_a1b2c3d4e5f6…`).

{: .important }
> **A chave aparece uma única vez**
>
> No momento da criação, o V3REvent mostra a chave **inteira** — é a **única vez**. Copie e guarde num lugar seguro (o gerenciador de senhas, ou direto na credencial da integração). Depois disso, a tela só mostra o **prefixo** (`v3re_a1b2c3…`) para você identificar a chave. Se perder a chave, não dá para recuperá-la: basta **gerar outra** e revogar a antiga.

## Usar a chave

O sistema externo envia a chave no **cabeçalho** de cada requisição:

```
X-V3REvent-Api-Key: v3re_a1b2c3d4e5f6...
```

No n8n, isso é um cabeçalho (header) na credencial ou no nó HTTP Request. Veja o passo a passo em **[Referência da API](/modulos/api-referencia/)** e nas **[receitas](/modulos/api-receitas-n8n/)**.

## Revogar e acompanhar

- **Revogar:** a qualquer momento você pode revogar uma chave. A integração que a usa **para de funcionar na hora** (passa a receber erro `401`). Use isso se a chave vazou, se a integração saiu do ar ou se você simplesmente não a usa mais.
- **Último uso:** a lista mostra a coluna **"último uso"**, com a data/hora em que a chave foi usada pela última vez. Serve para identificar chaves esquecidas (sem uso há muito tempo) e confirmar que uma integração nova começou a rodar.
- **Prefixo e status:** cada chave aparece com nome, prefixo, escopo, último uso e status (ativa/revogada).

## Boas práticas

{: .tip }
> - **Uma chave por integração.** Assim, se precisar revogar uma, as outras continuam funcionando — e o "último uso" te diz exatamente quem parou.
> - **Menor escopo possível.** Se a automação só cuida de um evento, dê a ela uma chave restrita àquele evento. Nunca use "todos os eventos" quando "um evento" basta.
> - **Nunca coloque a chave em lugar público** (um post, um repositório aberto, uma URL). Ela vai só no cabeçalho da requisição, no sistema que consome os dados.
> - **Revogue ao desligar** uma automação, em vez de deixar a chave viva "por via das dúvidas".

## LGPD: a chave é o controle de acesso aos dados pessoais

{: .important }
> O endpoint de **inscritos** (`/attendees`) devolve **dados pessoais** — nome, e-mail, CPF e os campos do formulário — com a **mesma completude do export** (XLSX/CSV). Ou seja: quem tem a chave consegue baixar a lista de participantes com PII.
>
> A **sua organização é a controladora** desses dados; a **chave é o controle de acesso** a eles. Por isso: crie chaves com o **menor escopo** necessário, **revogue** as que não usa, acompanhe o **"último uso"** e trate cada chave com o mesmo cuidado de uma senha. O V3REvent registra o uso da chave, o que ajuda na rastreabilidade exigida pela LGPD — mas a decisão de com quem compartilhar o acesso é sua.
