---
title: Política de Privacidade
parent: Legal
nav_order: 2
---

# Política de Privacidade

**V3REvent — Plugin de Gestão de Inscrições em Eventos para WordPress**

Versão 1.0 — Julho de 2026

---

{: .note }
> **Como ler este documento**
>
> O V3REvent é um plugin **auto-hospedado**: ele roda no WordPress do próprio
> usuário e os dados ficam no servidor dele. Por isso, este documento tem duas
> partes: **(A)** o que a V3RTECH faz com dados (praticamente nada) e **(B)**
> quais dados pessoais o plugin trata no ambiente do usuário — informação
> essencial para que o usuário cumpra a LGPD como **controlador** desses dados.

---

## Parte A — O papel da V3RTECH

**A.1.** A V3RTECH é a **fornecedora do software**. Ela desenvolve e distribui o plugin, mas **não hospeda, não acessa e não recebe** os dados de eventos, inscritos ou pagamentos processados pelo V3REvent na instalação do usuário. Não há envio automático desses dados para a V3RTECH ("phone-home").

**A.2.** Eventuais dados de contato que o usuário forneça diretamente à V3RTECH (por exemplo, ao solicitar suporte ou adquirir o plugin) são tratados apenas para essa finalidade, conforme a LGPD (Lei nº 13.709/2018). O canal **Enviar Feedback** do plugin só envia os seus dados de organização à V3RTECH **se você marcar o consentimento** correspondente, e nunca inclui segredos.

**A.3.** Encarregado de Proteção de Dados (DPO) da V3RTECH: [dpo@v3rtech.com.br](mailto:dpo@v3rtech.com.br).

---

## Parte B — Dados tratados pelo plugin (responsabilidade do usuário)

{: .important }
> **Quem é o controlador**
>
> Ao usar o V3REvent para tratar dados de participantes, **você (o organizador,
> usuário do plugin) é o controlador** desses dados pessoais, nos termos da LGPD.
> Cabe a você definir a base legal, informar os titulares e atender aos direitos
> deles. Esta seção descreve o que o plugin coleta, para você cumprir esse papel.

### B.1. Dados que o plugin armazena no seu servidor

| Dado | Origem | Onde é usado |
|---|---|---|
| Nome, e-mail, telefone e organização do responsável pela inscrição | Formulário de inscrição | Comunicação, recibo e relatório |
| Dados de cada participante (nome, CPF, e-mail e demais campos que você configurar) | Formulário / importação de planilha | Registro da inscrição, confirmação, credencial |
| Consentimento de tratamento e, quando aplicável, de networking | Formulário de inscrição | Base do tratamento e do QR de contato |
| Código de inscrição, status de pagamento e horário de check-in | Processamento do pedido e credenciamento | Controle de inscrições e presença |
| Dados do pedido no WooCommerce (inclui dados de cobrança) | Checkout do WooCommerce | Processamento do pagamento |

Todos esses dados ficam **no banco de dados do seu WordPress**, sob sua guarda.

### B.2. Bases legais (a definir pelo controlador)

O tratamento desses dados costuma apoiar-se em **execução de contrato ou procedimentos preliminares** (Art. 7º, V da LGPD), na medida em que a inscrição é uma relação contratual entre organizador e inscrito. Recursos opcionais, como o **QR de networking** na credencial, apoiam-se em **consentimento** específico do titular (Art. 7º, I), capturado no formulário. Cabe a você confirmar a base adequada ao seu caso e informá-la aos titulares na sua própria política.

### B.3. Consentimento no formulário

O formulário de inscrição inclui um **consentimento obrigatório** do responsável, com link para a **sua** política de privacidade (configurável em Configurações → Avançado). Sem esse consentimento, a inscrição não é registrada. O consentimento de **networking** (que habilita o cartão de contato no QR da credencial) é **separado e opcional**.

### B.4. Serviços de terceiros (quando você os configurar)

O plugin só contata serviços externos que **você** configurar:

| Serviço | Dados enviados | Quando |
|---|---|---|
| **WooCommerce** e gateway de pagamento | Dados do pedido e de cobrança | No checkout da inscrição |
| **Serviço de e-mail** do seu WordPress (SMTP/host) | E-mails transacionais (confirmação, relatório, recibo, credencial) | Ao concluir inscrições |
| **Gotenberg** (geração de PDF), se configurado | Conteúdo do documento para renderizar o PDF | Ao gerar recibo/credencial em alta fidelidade |
| **Ferramentas de automação** via API/webhook, se configuradas | Eventos e dados de inscrição | Conforme sua automação |

A responsabilidade por contratar esses serviços e garantir conformidade (inclusive em eventuais transferências internacionais) é sua, na qualidade de controlador.

### B.5. Direitos dos titulares

Os titulares (os participantes e responsáveis) têm os direitos previstos na LGPD — confirmação, acesso, correção, eliminação, portabilidade, entre outros. Como controlador, você os atende diretamente: o plugin oferece ferramentas de **exportação** e **exclusão/anonimização** de dados de um titular (por código de inscrição ou e-mail), além das telas de inscrições e relatórios para localizar e conferir os registros.

### B.6. Retenção e eliminação

O V3REvent permite definir um **prazo de retenção** (Configurações → Avançado): os dados de inscritos de eventos já encerrados são **expurgados automaticamente** fora dessa janela. Você define o prazo conforme sua necessidade e obrigações legais. A exclusão manual de uma inscrição pelo painel também remove os respectivos registros.

### B.7. Segredos e segurança

- Chaves de API e credenciais de serviços ficam no seu servidor e **nunca** são incluídas no e-mail de feedback ao suporte nem em exportações de dados.
- Recomenda-se restringir o acesso ao painel administrativo (usando os papéis do plugin), manter o WordPress e o WooCommerce atualizados e usar HTTPS.

---

## Alterações nesta Política

Esta Política pode ser atualizada. A versão vigente estará sempre disponível em [docs.v3revent.v3rtech.com.br/legal/privacidade](https://docs.v3revent.v3rtech.com.br/legal/privacidade/).

---

## Contato

- **DPO da V3RTECH:** [dpo@v3rtech.com.br](mailto:dpo@v3rtech.com.br)
- **Suporte:** [suporte@v3rtech.com.br](mailto:suporte@v3rtech.com.br)
- **Comercial / Vendas:** [comercial@v3rtech.com.br](mailto:comercial@v3rtech.com.br)

---

*Versão 1.0 — Julho de 2026. Este documento descreve o comportamento do plugin quanto a dados pessoais e não substitui a assessoria jurídica que o controlador deve buscar para o seu caso concreto.*
