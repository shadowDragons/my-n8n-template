docs:https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.telegram/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=n8n-nodes-base.telegram

json:

```
{
  "nodes": [
    {
      "parameters": {
        "chatId": "-1002677235789",
        "text": "={{ $('AI Agent').item.json.output.title }}\n\n介绍：{{ $('AI Agent').item.json.output.summary }}\n\n标签：#{{ $json.property_category }}\n\n链接：https://tool.directory.cab/article/{{ $('AI Agent').item.json.output.slug }}",
        "additionalFields": {
          "appendAttribution": false
        }
      },
      "type": "n8n-nodes-base.telegram",
      "typeVersion": 1.2,
      "position": [
        -560,
        400
      ],
      "id": "cb372c1f-da99-408d-a62c-175250fe106b",
      "name": "Telegram",
      "webhookId": "d95aedae-4f69-4a3f-8b6a-5c77b4948ff0",
      "credentials": {
        "telegramApi": {
          "id": "jgd53Ex4Vf3d2xMr",
          "name": "Telegram account"
        }
      }
    }
  ],
  "connections": {},
  "pinData": {},
  "meta": {
    "instanceId": "c18b83340b516ec35503d90265d11efa191837c0f100386c72a196f9f7c5c10f"
  }
}
```