---
title: Gestão pelo site (sem wp-admin)
parent: Módulos
nav_order: 14
---

# Gestão pelo site (sem wp-admin)

Até a v1.68, gerenciar eventos exigia entrar no **painel administrativo do WordPress** (`wp-admin`). Isso é burocrático, e boa parte de quem deveria acompanhar um evento — coordenador, secretaria, equipe de portaria — **nem tem acesso a esse painel**, nem precisa aprender a usá-lo.

Agora existe um atalho: o shortcode `[v3revent_gestao]`, que o **administrador do site** cola numa página comum do WordPress. Quem tem papel em algum evento passa a acessar **Painel, Eventos (com o editor completo), Inscrições, Check-in e Relatórios** direto por ali — inclusive exportar as listas em **CSV, XLSX e PDF** — sem nunca entrar no `wp-admin`.

## Por que isto importa

Um voluntário que só faz credenciamento no dia não precisa (e não deveria) ter uma conta de administrador do WordPress — é mais superfície de risco do que ele usa. Com a página de gestão, você dá a ele um **link só do V3REvent**, ele entra com o próprio login e vê exatamente o que o papel dele permite. Nada de navegar o `wp-admin` procurando o menu certo, nada de acesso a outros plugins do site.

## Como montar a página

1. No WordPress, crie uma **página nova** (**Páginas → Adicionar nova**) — pode chamá-la "Gestão de eventos", por exemplo.
2. Adicione um bloco **Shortcode** (Gutenberg) ou o widget/bloco equivalente do seu construtor de página, e cole `[v3revent_gestao]`.
3. **Publique** a página.

Pronto — a URL dessa página é o link que você compartilha com quem vai gerenciar eventos.

{: .tip }
> **Não precisa aparecer no menu do site**
>
> A página não entra automaticamente em nenhum menu de navegação, e o V3REvent a marca como **não indexável** para buscadores (ela é área de trabalho, não conteúdo do site). Deixe-a "solta" — acessível só por quem tem o link — ou coloque atrás de um menu interno, como preferir.

## O que aparece — e para quem

A tela é a **mesma gestão** do painel administrativo, só em outra casca: as mesmas telas, os mesmos dados, os mesmos botões.

![Página de gestão aberta no site, mostrando o Painel com os indicadores do evento](/assets/screenshots/gestao-frontend-painel.png)

- **Painel** — indicadores gerais.
- **Eventos** — lista completa, com o **editor de evento** por trás de cada linha (as mesmas abas do `wp-admin`: detalhes, campos, preços, aparência, equipe…).
- **Inscrições** — lista, filtros, troca de status e exportação.
- **Check-in** — leitura de QR e entrada manual, pensado para uso **em pé, no celular**, na portaria.
- **Relatórios** — indicadores do evento, participantes, presença e exportações.

![Check-in aberto no celular, com o menu de navegação em abas no topo](/assets/screenshots/gestao-frontend-mobile-checkin.png)

{: .important }
> **As permissões são exatamente as mesmas do wp-admin — nem mais, nem menos**
>
> A página de gestão **não cria nenhum acesso novo**: ela usa o mesmo papel que a pessoa já tem no plugin (veja **[Primeiros passos → Entender os papéis de acesso](/primeiros-passos/#4-entender-os-papéis-de-acesso)**). Um **Coordenador de Eventos** só vê e edita os eventos em que foi designado — inclusive nas exportações — do mesmo jeito que veria no `wp-admin`. Não existe um "modo site" mais permissivo nem mais restrito.

## O que continua só no wp-admin

Duas coisas ficam de fora de propósito:

- **Configurações da organização.** É a única área do plugin que **não** vai para a página de gestão — perfil da organização, e-mails, aparência global, LGPD e administradores continuam exclusivos do **V3REvent → Configurações**, no `wp-admin`. Veja **[Configurações](/modulos/configuracoes/)**.
- **Editar o pedido no WooCommerce.** Na lista de **Inscrições**, o número do pedido (`Pedido #123`) aparece sempre — mas, na página de gestão, ele vem **sem link**: editar um pedido é uma tela do WooCommerce que só existe dentro do `wp-admin`. Para isso, é preciso acessar o painel.

## Quem não tem acesso

Quem abre a página **sem estar logado** vê apenas um aviso, com um link para entrar — nenhum dado de evento ou de inscrito aparece:

> Entre para acessar a gestão do V3REvent.

Quem está **logado**, mas não tem papel em **nenhum** evento do plugin, vê este outro aviso:

> Sua conta não tem acesso à gestão do V3REvent. Fale com quem administra o site.

{: .tip }
> **Resolvendo o segundo aviso**
>
> Se alguém da sua equipe cai nesse aviso, é porque ninguém a atribuiu a um evento ainda. Um **Administrador da Organização** resolve na aba **Equipe** do editor do evento correspondente — atribua **Coordenador de Eventos** ou **Equipe de Evento**, conforme o caso. Veja **[Editor de evento → Equipe](/modulos/editor-evento/#equipe)**.

## Dicas e armadilhas

- **Um link por pessoa, não um link geral divulgado.** Trate a URL da página de gestão como você trataria o link do `wp-admin`: não é para colocar num cartaz nem numa página pública de navegação. Quem não tiver papel só vê o aviso, mas não há motivo para expor o caminho à toa.
- **Funciona no celular de propósito.** O Check-in nasceu pensando em uso na portaria, em pé, com uma mão só — é a tela mais provável de ser usada fora de uma mesa.
- **"Meu evento sumiu" quase sempre é papel, não bug.** Antes de investigar, confirme em que evento a pessoa foi designada — veja a nota de permissões acima.

## Quando dá errado

| O que a pessoa vê | O que significa | O que fazer |
|---|---|---|
| "Entre para acessar a gestão do V3REvent." | Não está logada no WordPress. | Clique no link do aviso e entre com o usuário do WordPress. |
| "Sua conta não tem acesso à gestão do V3REvent. Fale com quem administra o site." | Está logada, mas sem papel em nenhum evento. | Um Administrador da Organização atribui o papel na aba **Equipe** do evento. |
| A tela abre, mas fica "vazia" ou dá erro ao carregar dados | O WooCommerce está inativo no site (o V3REvent depende dele). | Verifique com quem administra o site se o WooCommerce está ativo. |
| Número do pedido aparece sem link para clicar | Comportamento esperado — editar pedido é exclusivo do `wp-admin`. | Acesse o painel para editar o pedido no WooCommerce. |

{: .note }
> A página de gestão reaproveita a mesma API do V3REvent que o painel usa — não é uma cópia dos dados, é a mesma gestão. O que muda é só onde ela é exibida.
