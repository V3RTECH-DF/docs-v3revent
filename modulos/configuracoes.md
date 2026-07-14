---
title: Configurações
parent: Módulos
nav_order: 7
---

# Configurações

As **Configurações** valem para **toda a organização** e servem de base para os eventos. Ficam organizadas em cinco abas — **Organização, E-mails, Aparência, Avançado e Administradores** — e são acessíveis ao **Administrador da Organização**. Um botão **Salvar** grava as alterações.

## Organização

Os dados da organização que promove os eventos — reaproveitados em recibos, credenciais e e-mails.

![Configurações — aba Organização](/assets/screenshots/config-organizacao.png)

- **Nome** e **CNPJ** (aceita o formato **alfanumérico** da RFB, ex.: `12.ABC.345/01DE-35`, com validação do dígito verificador);
- **Endereço** e **contato**;
- **Logo** (pela Biblioteca de Mídia).

{: .tip }
> Preencher bem esta aba é o que faz recibos e credenciais saírem prontos, com a sua identidade, sem retrabalho a cada evento.

## E-mails

Os templates da comunicação automática.

![Configurações — aba E-mails](/assets/screenshots/config-emails.png)

- **Remetente** (nome e e-mail);
- **Template de confirmação** (enviado a cada participante);
- **Template de relatório** (enviado ao responsável).

Os templates aceitam **variáveis** (como o nome do evento, o nome do participante e o **código de inscrição**), exibidas como dica na própria tela. Cada evento pode sobrescrever esses textos.

## Aparência

As cores e a fonte **padrão** que os novos eventos herdam (e que cada evento pode sobrepor na sua aba Aparência).

![Configurações — aba Aparência](/assets/screenshots/config-aparencia.png)

## Avançado

Privacidade, geração de PDF e manutenção.

![Configurações — aba Avançado](/assets/screenshots/config-avancado.png)

- **Retenção de dados (LGPD)** — por quantos meses manter os dados de inscritos de eventos encerrados (0 = desativado). Fora dessa janela, o expurgo é automático.
- **URL da política de privacidade** — o link que aparece no consentimento do formulário.
- **Gotenberg** — campo reservado para o endpoint de um serviço externo de geração de PDF de alta fidelidade. Aparece marcado como **"Em breve"** e ainda não é editável; enquanto isso, o plugin gera os PDFs internamente.
- **Excluir dados ao desinstalar** — opção para remover tudo do banco caso o plugin seja desinstalado.

{: .important }
> **Cuidado com "excluir ao desinstalar"**
>
> Com essa opção ligada, desinstalar o plugin **apaga permanentemente** eventos, inscrições e configurações. É uma ação **irreversível** — só a mantenha marcada se tiver certeza e um backup.

## Administradores

Define quem são os **Administradores da Organização** — os usuários com acesso a todo o plugin (qualquer evento e as próprias Configurações). Busque um usuário do WordPress e adicione-o à lista.

{: .note }
> Este é o topo da hierarquia de acesso. **Coordenadores** e **Equipe** são atribuídos por evento, na aba **Equipe** do editor de evento — não aqui. Veja os papéis em **[Primeiros passos](/primeiros-passos/)**.
