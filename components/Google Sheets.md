docs:https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.googlesheets/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=n8n-nodes-base.googleSheets

json:

```
{
  "nodes": [
    {
      "parameters": {
        "operation": "appendOrUpdate",
        "documentId": {
          "__rl": true,
          "value": "1up956lFkOyTxSCb0pxmufjz3VksUKA_CS3tMgxwD2XM",
          "mode": "id"
        },
        "sheetName": {
          "__rl": true,
          "value": "reddit",
          "mode": "name"
        },
        "columns": {
          "mappingMode": "defineBelow",
          "value": {
            "内容": "={{ $json.selftext }}",
            "标题": "={{ $json.title }}",
            "链接": "={{ $json.url }}"
          },
          "matchingColumns": [
            "标题"
          ],
          "schema": [
            {
              "id": "标题",
              "displayName": "标题",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true,
              "removed": false
            },
            {
              "id": "内容",
              "displayName": "内容",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "链接",
              "displayName": "链接",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            }
          ],
          "attemptToConvertTypes": false,
          "convertFieldsToString": false
        },
        "options": {}
      },
      "type": "n8n-nodes-base.googleSheets",
      "typeVersion": 4.6,
      "position": [
        100,
        20
      ],
      "id": "e636639f-fad7-4cac-bb23-bb56be7ec580",
      "name": "Google Sheets",
      "credentials": {
        "googleSheetsOAuth2Api": {
          "id": "Nl41fcUY0NozeVjw",
          "name": "Google Sheets account"
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