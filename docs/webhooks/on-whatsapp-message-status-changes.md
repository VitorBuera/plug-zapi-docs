---
id: on-whatsapp-message-status-changes
title: Status da mensagem
---

## Método

#### `POST` on-whatsapp-message-status-changes

## Conceituação

Esse é o webhook de retorno do status da mensagem

:::caution Atenção

O PlugZapi não aceita webhooks que não sejam HTTPS

:::

---

## Atualizando Webhook

Para atualizar a rota do webhook é possível fazer isso pela API ou pelo painel administrativo.

### API

#### /update-webhook-status

`PUT` https://api.plugzapi.com.br/instances/SUA_INSTANCIA/token/SEU_TOKEN/update-webhook-message-status

#### Request Body

#### Body

```json
{
  "value": "https://endereco-do-seu-sistema.com.br/instancia/SUA_INSTANCIA/status"
}
```

---

### Painel Administrativo

![img](../../img/status.png)

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| status | string | Tipo do status no qual a mensagem se encontra. |
| id | string | Identificador(es) da(s) mensagem(ns). |
| phone | string | Número de telefone de destino da mensagem. |
| momment | string | Momento em que a instância foi desconectada do número. |
| type | string | Tipo do evento da instância, nesse caso será "MessageStatusCallback". |

---

## Response

### 200

```json
{
  "status": "MESSAGE_RECEIVED",
  "ids": ["999999999999999999999"],
  "momment": 1632234645000,
  "phone": "5544999999999",
  "type": "MessageStatusCallback"
}
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

<!--
## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/PlugZapi/plugzapi-docs/main/json-examples/on-whatsapp-message-status-changes.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe> -->
