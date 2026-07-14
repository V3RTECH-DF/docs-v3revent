---
title: Primeiros passos
nav_order: 2
---

# Primeiros passos

O V3REvent é um plugin de WordPress. Você o instala no seu próprio site e trabalha inteiramente dentro do painel (`wp-admin`) — sem contas externas nem mensalidade de plataforma. Como ele cobra inscrições, depende do **WooCommerce** para o carrinho e o pagamento.

## 1. Requisitos

{: .note }
> **Antes de instalar, confira o ambiente**
>
> - **WordPress** 6.0 ou superior
> - **PHP** 8.0 ou superior
> - **WooCommerce** 7.0 ou superior, **ativo** (obrigatório — é ele que processa o pagamento)

Se o WooCommerce não estiver ativo, o V3REvent avisa e as telas de inscrição não funcionam. Eventos **gratuitos** são possíveis: basta configurar o preço como R$ 0 — o pedido passa pelo WooCommerce mesmo assim.

## 2. Instalar e ativar

1. No painel do WordPress, acesse **Plugins → Adicionar novo → Enviar plugin**.
2. Selecione o arquivo `.zip` do V3REvent e clique em **Instalar agora**.
3. Depois de instalado, clique em **Ativar**.

Ao ativar, um novo item **V3REvent** aparece no menu lateral do WordPress. A ativação também cria as tabelas do plugin e prepara os papéis de acesso (veja o item 4).

## 3. Preencher o perfil da organização

Antes de criar o primeiro evento, preencha os dados da organização que **promove** os eventos. Eles são reaproveitados em recibos, credenciais e e-mails.

Acesse **V3REvent → Configurações → Organização** e informe:

- **Nome da organização** e **CNPJ** (aceita o novo formato **alfanumérico** da RFB — ex.: `12.ABC.345/01DE-35`);
- **Endereço** e **dados de contato**;
- **Logo** (via Biblioteca de Mídia do WordPress).

{: .tip }
> **Faça isso uma vez só**
>
> Bem preenchido, o perfil da organização vira a base de todo documento que o plugin gera. O recibo que o pagador recebe e a credencial do participante já saem com o seu nome, CNPJ e logo — sem retrabalho a cada evento.

Detalhes de cada campo em **[Configurações](/modulos/configuracoes/)**.

## 4. Entender os papéis de acesso

O V3REvent controla quem pode fazer o quê por meio de **três papéis**. Isso permite dividir o trabalho sem dar acesso total a todo mundo.

| Papel | Alcance | O que faz |
|---|---|---|
| **Administrador da Organização** | Todo o plugin | Cria e gerencia qualquer evento, define equipes, ajusta as Configurações e cuida da privacidade (LGPD). |
| **Coordenador de Eventos** | Por evento | Gerencia tudo de **um evento específico** — configuração, inscrições, relatórios, credenciais — mas não mexe nas Configurações globais. |
| **Equipe de Evento** | Por evento | Foco **operacional**: acompanha inscrições e faz o **check-in** no dia. Não altera a configuração do evento. |

Quem instala o plugin (usuários que já administram o WordPress) entra automaticamente como **Administrador da Organização**. A partir daí, você designa coordenadores e equipe **por evento**, na aba **Equipe** do editor de evento.

{: .important }
> **Por que isso importa**
>
> Dar a cada pessoa só o acesso de que ela precisa é o **princípio do menor privilégio** — reduz erros e protege os dados dos inscritos. Um voluntário que só faz credenciamento no dia deve ser **Equipe de Evento**, não administrador.

## 5. Próximo passo

Com a organização preenchida, você está pronto para **[criar um evento de ponta a ponta](/criar-evento/)** — do rascunho à primeira inscrição paga.
