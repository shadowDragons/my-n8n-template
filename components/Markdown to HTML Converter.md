docs:https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-base.markdown/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=n8n-nodes-base.markdown

json:

```
{
  "nodes": [
    {
      "parameters":     {
        "mode": "markdownToHtml",
        "markdown": "={{ $json.Post_solution }}",
        "options": {}
      },
      "type": "n8n-nodes-base.markdown",
      "typeVersion": 1,
      "position": [
        320,
        -20
      ],
      "id": "a297e656-7203-47d7-94ab-2660a69a1c6d",
      "name": "Markdown"
    }
  ],
  "connections": {
    "Markdown": {
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