docs:https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.notion/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=n8n-nodes-base.notion

json:

```
{
  "nodes": [
    {
      "parameters": {
        "resource": "databasePage",
        "databaseId": {
          "__rl": true,
          "value": "14cbfc15-6863-800c-a6ff-f113eeaba247",
          "mode": "list",
          "cachedResultName": "字节工具导航站",
          "cachedResultUrl": "https://www.notion.so/14cbfc156863800ca6fff113eeaba247"
        },
        "title": "={{ $json.output.title }}",
        "propertiesUi": {
          "propertyValues": [
            {
              "key": "summary|rich_text",
              "textContent": "={{ $json.output.summary }}"
            },
            {
              "key": "date|date",
              "date": "={{ $json.output.date }}"
            },
            {
              "key": "category|select",
              "selectValue": "={{ $json.output.category }}"
            },
            {
              "key": "slug|rich_text",
              "textContent": "={{ $json.output.slug }}"
            },
            {
              "key": "tags|multi_select",
              "multiSelectValue": "={{ $json.output.tags }}"
            },
            {
              "key": "url|url",
              "urlValue": "={{ $json.output.url }}"
            },
            {
              "key": "type|select",
              "selectValue": "={{ $json.output.type }}"
            },
            {
              "key": "status|select",
              "selectValue": "Published"
            }
          ]
        },
        "blockUi": {
          "blockValues": [
            {
              "textContent": "={{ $json.output.content }}"
            }
          ]
        },
        "options": {}
      },
      "type": "n8n-nodes-base.notion",
      "typeVersion": 2.2,
      "position": [
        -560,
        180
      ],
      "id": "084389c8-9c54-4158-89ff-0550c873b448",
      "name": "Notion",
      "credentials": {
        "notionApi": {
          "id": "p0vBw93aPC87iHmp",
          "name": "Notion account"
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