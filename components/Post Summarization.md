docs:https://docs.n8n.io/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.chainsummarization/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=%40n8n%2Fn8n-nodes-langchain.chainSummarization


json:

```
{
  "nodes": [
    {
      "parameters": {
        "options": {
          "summarizationMethodAndPrompts": {
            "values": {
              "combineMapPrompt": "Write a concise summary of the following，输出中文:\n\n\n\"{text}\"\n\n\nCONCISE SUMMARY:",
              "prompt": "Write a concise summary of the following，输出中文:\n\n\n\"{text}\"\n\n\nCONCISE SUMMARY:"
            }
          }
        }
      },
      "id": "c9a75b92-735e-4282-8296-5e60e1c3d0bb",
      "name": "Post Summarization",
      "type": "@n8n/n8n-nodes-langchain.chainSummarization",
      "position": [
        80,
        -440
      ],
      "typeVersion": 2
    },
    {
      "parameters": {
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.lmChatDeepSeek",
      "typeVersion": 1,
      "position": [
        80,
        -280
      ],
      "id": "cc72a723-47ab-4279-9dc7-de56e93fb377",
      "name": "DeepSeek Chat Model3",
      "credentials": {
        "deepSeekApi": {
          "id": "HG2MiMSzHpKDJXkh",
          "name": "DeepSeek account"
        }
      }
    }
  ],
  "connections": {
    "DeepSeek Chat Model3": {
      "ai_languageModel": [
        [
          {
            "node": "Post Summarization",
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