docs:https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.gmail/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=n8n-nodes-base.gmail

json:

```
{
  "nodes": [
    {
      "parameters": {
        "sendTo": "shadowdragon4399@gmail.com",
        "subject": "=reddit总结-{{ $json.reddit }}",
        "emailType": "text",
        "message": "={{ $json.markdown }}",
        "options": {}
      },
      "type": "n8n-nodes-base.gmail",
      "typeVersion": 2.1,
      "position": [
        -20,
        180
      ],
      "id": "eff7bd84-1682-4207-a8d0-422ad4ea9ceb",
      "name": "Gmail",
      "webhookId": "643ca605-a969-458e-a9c0-c879376bae8c",
      "credentials": {
        "gmailOAuth2": {
          "id": "gikZLZ6HdSttDchP",
          "name": "Gmail account"
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