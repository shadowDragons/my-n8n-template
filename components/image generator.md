docs:使用 fastgpt 的 api

```
{
  "nodes": [
    {
      "parameters": {
        "method": "POST",
        "url": "https://api.fastgpt.in/api/v1/chat/completions",
        "authentication": "genericCredentialType",
        "genericAuthType": "httpHeaderAuth",
        "sendBody": true,
        "specifyBody": "json",
        "jsonBody": "={\n  \"model\": \"flux-1\",\n  \"messages\": [\n    {\n      \"role\": \"user\",\n      \"content\": \"{{ $('AI Agent').item.json.output.cover_image_prompt }}\"\n    }\n  ],\n  \"stream\": false\n}",
        "options": {}
      },
      "type": "n8n-nodes-base.httpRequest",
      "typeVersion": 4.2,
      "position": [
        1240,
        -140
      ],
      "id": "9d45b031-e14c-4e10-bb07-1a636f2fb491",
      "name": "HTTP Request",
      "credentials": {
        "httpHeaderAuth": {
          "id": "r0sEHkWmnEZple0z",
          "name": "fastgpt"
        }
      }
    },
    {
      "parameters": {
        "jsCode": "const content = $input.first().json.choices[0].message.content;\nconst match = content.match(/\\((https?:\\/\\/[^\\)]+)\\)/);\nreturn [{\n  ImgUrl: match ? match[1] : ''\n}];"
      },
      "type": "n8n-nodes-base.code",
      "typeVersion": 2,
      "position": [
        1460,
        -140
      ],
      "id": "1fcc0f8d-0bfa-49c9-af1d-32f2a2ef2285",
      "name": "Code"
    }
  ],
  "connections": {
    "HTTP Request": {
      "main": [
        [
          {
            "node": "Code",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "Code": {
      "main": [
        []
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
