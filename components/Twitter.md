docs:https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.twitter/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=n8n-nodes-base.twitter

json:

```
{
  "nodes": [
    {
      "parameters": {
        "text": "=#每日工具推荐\n{{ $('AI Agent').first().json.output }}\n工具链接👉：https://tool.directory.cab/article/{{ $json.property_slug }}",
        "additionalFields": {}
      },
      "type": "n8n-nodes-base.twitter",
      "typeVersion": 2,
      "position": [
        1460,
        120
      ],
      "id": "7f3ff09f-7346-4d76-a448-f71b6a23b223",
      "name": "Create Tweet",
      "credentials": {
        "twitterOAuth2Api": {
          "id": "IYbFleDCi8ezqsN9",
          "name": "X account"
        }
      }
    }
  ],
  "connections": {},
  "pinData": {},
  "meta": {
    "templateCredsSetupCompleted": true,
    "instanceId": "c18b83340b516ec35503d90265d11efa191837c0f100386c72a196f9f7c5c10f"
  }
}
```
