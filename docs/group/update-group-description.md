---
id: update-group-description
title: Alterar descrição
---

## Método

#### /update-group-description

`POST` https://api.plugzapi.com.br/instances/SUA_INSTANCIA/token/SEU_TOKEN/update-group-description

## Conceituação

Este método permite você alterar a descrição do grupo.

:::caution Atenção

Atenção somente administradores podem alterar as preferências do grupo.

:::

:::caution Atenção

No dia 4 de novembro de 2021 o whatsapp alterou a formato da criação de novos grupos, antes: "phone": "5511999999999-1623281429" agora: "phone": "120363019502650977-group"

:::

---

## Atributos

### Obrigatórios

| Atributos        |  Tipo  | Descrição                                  |
| :--------------- | :----: | :----------------------------------------- |
| groupId          | string | ID/Fone do grupo                           |
| groupDescription | string | Atributo para alterar a descrição do grupo |

---

#### Body

```json

Forma antiga -
  {
    "groupId": "5511999999999-1623281429",
    "groupDescription": "descrição do grupo"
  }

----------------------------------------

Forma nova -
  {
    "groupId": "120363019502650977-group",
    "groupDescription": "descrição do grupo"
  }

```

---

## Response

### 200

| Atributos | Tipo    | Descrição                                           |
| :-------- | :------ | :-------------------------------------------------- |
| value     | boolean | true caso tenha dado certo e false em caso de falha |

**Exemplo**

```json
{
  "value": true
}
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Webhook Response

Link para a response do webhook (ao receber)

[Webhook](../webhooks/on-message-received#response)

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/PlugZapi/plugzapi-docs/main/json-examples/update-group-description.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
