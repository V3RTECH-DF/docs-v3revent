---
title: 'Documentos: recibo, credencial e certificado'
parent: Módulos
nav_order: 10
---

# Documentos: recibo, credencial e certificado

O V3REvent gera documentos automáticos a partir de um evento: o **recibo** (para o pagador), a **credencial** (para cada participante) e o **certificado de participação** (para quem é elegível). Todos usam a identidade do evento e os dados da organização, e têm um **link público por código** — imprimível e com versão em PDF.

## Recibo

Ao concluir o pedido, o **responsável (pagador)** recebe por e-mail um **recibo em PDF** com:

- o logo e as cores (do evento, com recuo para a organização e, por fim, o V3REvent);
- os **dados da organização** (nome, CNPJ, endereço);
- o **evento**, a **lista de inscritos** (nome e modalidade), a **quantidade**, o **valor por inscrito e o total pago**, o **número do pedido** e um **código de recibo**;
- um selo **PAGO**.

![Recibo público do evento](/assets/screenshots/recibo-publico.png)

O e-mail traz também um **link permanente** para reemissão (`recibo/{código}`): a versão em tela é imprimível, e é possível baixar o PDF a qualquer momento.

{: .important }
> **Recibo não é nota fiscal.** O recibo é um **comprovante de pagamento** de uso interno. A emissão de documento fiscal, quando exigível, é obrigação do organizador, feita à parte.

## Credencial

Cada participante confirmado tem uma **credencial** (crachá) com a logo e as cores do evento, em um dos modelos disponíveis, contendo um **QR**.

![Credencial pública com QR](/assets/screenshots/credencial-publica.png)

### O QR e o networking consentido

- **Padrão:** o QR aponta apenas para a página de validação da credencial (`credencial/{código}`), usada no **check-in**.
- **Com consentimento de networking:** o QR passa a carregar um **cartão de contato (vCard)** — nome, e-mail, telefone, organização e cargo, conforme o mapeamento que você definiu — mantendo o código embutido para o check-in.

### Envio e geração em lote

- **Envio automático** (opcional por evento): a credencial em PDF vai ao e-mail de cada inscrito.
- **Geração em lote:** um PDF com todas as credenciais (uma por página), pronto para a gráfica.

{: .note }
> O QR da credencial é o que liga o participante ao **[Check-in](/modulos/checkin/)**. Mesmo quando o QR carrega o vCard de networking, o código de inscrição continua embutido — então a leitura no credenciamento funciona igual.

## Certificado de participação

Quem é elegível recebe um **certificado** na logo e nas cores do evento, em um dos modelos disponíveis (ex.: Clássico e Moderno), com a carga horária quando você a informa.

![Certificado de participação](/assets/screenshots/certificado-publico.png)

- **Elegibilidade por modalidade:** em evento **presencial**, é elegível quem fez **check-in**; em evento **virtual**, quem tem a inscrição **confirmada**.
- **Emissão:** você ativa o certificado, escolhe o modelo e a carga horária na aba **[Certificado](/modulos/editor-evento/)** do editor, e **envia por e-mail** aos elegíveis (envio manual, quando quiser).
- **Verificação:** cada certificado tem um **link público** (`certificado/{código}`) que serve de comprovação — o código é a chave de validação. Há versão imprimível em tela e em PDF.

{: .note }
> O certificado é liberado **só para quem é elegível**. Em evento presencial, isso liga o certificado ao **[Check-in](/modulos/checkin/)**: sem presença registrada, não há certificado.

## Geração de PDF

Os documentos são gerados **internamente pelo plugin**, sem depender de nenhum serviço externo — no limite, com uma versão imprimível em HTML. Para **fidelidade máxima** ao layout, está prevista a integração com o serviço **Gotenberg** (campo marcado como "Em breve" em **[Configurações → Avançado](/modulos/configuracoes/)**).
