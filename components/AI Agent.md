docs:https://docs.n8n.io/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=%40n8n%2Fn8n-nodes-langchain.agent

json:

```
{
  "nodes": [
    {
      "parameters": {
        "promptType": "define",
        "text": "=你是一位推荐工具的爆款推特写作专家，请针对该产品名称和产品简介，写一篇推文，字数限制在60以内，以痛点问题开头，不要加标签，不要任何多余信息\n\n产品名称：{{ $json.name }}\n产品信息：{{ $json.property_summary }}\n\n\n ",
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.agent",
      "typeVersion": 2,
      "position": [
        920,
        120
      ],
      "id": "a998d7a1-3319-4b0f-9c22-9a2636b61bbf",
      "name": "AI Agent"
    },
    {
      "parameters": {
        "model": "deepseek/deepseek-chat-v3-0324:free",
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.lmChatOpenRouter",
      "typeVersion": 1,
      "position": [
        920,
        300
      ],
      "id": "3df381e4-7d88-4bff-aa3a-17c671ca0443",
      "name": "OpenRouter Chat Model",
      "credentials": {
        "openRouterApi": {
          "id": "buuT1LirpxP5bKK6",
          "name": "OpenRouter account"
        }
      }
    }
  ],
  "connections": {
    "AI Agent": {
      "main": [
        []
      ]
    },
    "OpenRouter Chat Model": {
      "ai_languageModel": [
        [
          {
            "node": "AI Agent",
            "type": "ai_languageModel",
            "index": 0
          }
        ]
      ]
    }
  },
  "pinData": {},
  "meta": {
    "templateCredsSetupCompleted": true,
    "instanceId": "c18b83340b516ec35503d90265d11efa191837c0f100386c72a196f9f7c5c10f"
  }
}
```
