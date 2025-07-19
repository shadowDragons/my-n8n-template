docs: https://docs.n8n.io/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.sentimentanalysis/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=%40n8n%2Fn8n-nodes-langchain.sentimentAnalysis

json:

```
{
  "nodes": [
    {
      "parameters": {
        "inputText": "={{ $json.postcontent }}",
        "options": {}
      },
      "id": "bc55b468-f160-4950-af4e-a352d2b6560f",
      "name": "Post Sentiment Analysis",
      "type": "@n8n/n8n-nodes-langchain.sentimentAnalysis",
      "position": [
        900,
        -380
      ],
      "typeVersion": 1
    },
    {
      "parameters": {
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.lmChatDeepSeek",
      "typeVersion": 1,
      "position": [
        900,
        -200
      ],
      "id": "7b5064bd-cb7f-468f-b6b4-617ef0e03f7b",
      "name": "DeepSeek Chat Model1",
      "credentials": {
        "deepSeekApi": {
          "id": "HG2MiMSzHpKDJXkh",
          "name": "DeepSeek account"
        }
      }
    }
  ],
  "connections": {
    "DeepSeek Chat Model1": {
      "ai_languageModel": [
        [
          {
            "node": "Post Sentiment Analysis",
            "type": "ai_languageModel",
            "index": 0
          }
        ]
      ]
    }
  },
  "pinData": {},
  "meta": {
    "instanceId": "c18b83340b516ec35503d90265d11efa191837c0f100386c72a196f9f7c5c10f"
  }
}
```