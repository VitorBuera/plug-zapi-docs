---
id: send-message-contact
title: Enviar contato
---

## Método

#### /send-contact

`POST` https://api.plugzapi.com.br/instances/SUA_INSTANCIA/token/SEU_TOKEN/send-contact

---

## Conceituação

Simples e objetivo este método permite você enviar um contato, você não precisa ter ele em seus contatos, basta preencher os atributos do metodo com informações do contato e enviar.

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| phone | string | Telefone (ou ID do grupo para casos de envio para grupos) do destinatário no formato DDI DDD NUMERO Ex: 551199999999. **IMPORTANTE** Envie somente números, sem formatação ou máscara |
| contactName | string | Nome do contato |
| contactPhone | string | Telefone do contato que você quer compartilhar |
| contactBusinessDescription | string | Brever descrição sobre o contato (não é exibido no whatsapp web) |

### Opcionais

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| messageId | String | Atributo utilizado para responder uma mensagem do chat, basta adicionar o messageId da mensagem que queira responder neste atributo |
| delayMessage | number | Nesse atributo um delay é adicionado na mensagem. Você pode decidir entre um range de 1~15 sec, significa quantos segundos ele vai esperar para enviar a próxima mensagem. (Ex "delayMessage": 5, ). O delay default caso não seja informado é de 1~3 sec |

---

## Request Body

```json
{
  "phone": "5511999999999",
  "contactName": "PlugZapi Contato",
  "contactPhone": "554498398733",
  "contactBusinessDescription": "PlugZapi Mais software, menos esforço"
}
```

---

## Response

### 200

| Atributos | Tipo   | Descrição      |
| :-------- | :----- | :------------- |
| zaapId    | string | id no plugzapi |
| messageId | string | id no whatsapp |

Exemplo

```json
{
  "zaapId": "3999984263738042930CD6ECDE9VDWSA",
  "messageId": "D241XXXX732339502B68"
}
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Webhook Response

Link para a response do webhook (ao receber)

[Webhook](../webhooks/on-message-received#exemplo-de-retorno-de-contato)

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/PlugZapi/plugzapi-docs/main/json-examples/send-contact.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
