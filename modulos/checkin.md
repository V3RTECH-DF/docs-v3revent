---
title: Check-in
parent: Módulos
nav_order: 6
---

# Check-in

A tela **Check-in** é o credenciamento do dia: você lê o QR da credencial (ou digita o código) e marca a presença do participante em segundos. É a ferramenta da **Equipe de Evento** e do **Coordenador**.

![Tela de Check-in com leitor de QR e entrada manual](/assets/screenshots/checkin.png)

## Duas formas de marcar presença

- **Leitor de QR por câmera** — aponte a câmera para o QR da credencial; ao reconhecer, a presença é marcada.
- **Entrada manual** — digite o **código de inscrição** (`XXXX-XXXX`) quando a câmera não estiver disponível.

Há ainda uma terceira via, fora desta tela: abrindo a **página da credencial** pelo celular, a equipe logada vê um botão **Confirmar presença / Desfazer**.

## O retorno visual

Cada leitura mostra um retorno grande e colorido:

- **Verde** — presença registrada agora;
- **Amarelo** — a pessoa **já havia entrado** (não duplica);
- **Vermelho** — código **inválido** ou não encontrado.

Um **contador de sessão** acompanha quantos você já credenciou.

## Idempotente e reversível

- Ler o mesmo QR duas vezes **não** cria presença dupla nem muda o horário — apenas avisa que já estava presente.
- É possível **desfazer** um check-in feito por engano.

{: .tip }
> **Prepare o credenciamento**
>
> Teste a leitura de QR no local no dia anterior, garanta boa iluminação e tenha o **código manual** como plano B. Confirme que cada pessoa da recepção tem login com o papel **Equipe de Evento** naquele evento — sem isso, o botão de confirmar presença não aparece.

{: .note }
> A presença marcada aqui alimenta a coluna de **Presença** e a exportação de **presentes** em **[Relatórios](/modulos/relatorios/)**.
