docs:https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.reddit/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=n8n-nodes-base.reddit

json:

```
{
  "nodes": [
    {
      "parameters": {
        "operation": "getAll",
        "subreddit": "={{ $json.subreddit }}",
        "limit": 10,
        "filters": {
          "category": "top"
        }
      },
      "id": "06a7de46-3871-4a71-b865-1dbf19be2494",
      "name": "获取热门帖子",
      "type": "n8n-nodes-base.reddit",
      "typeVersion": 1,
      "position": [
        -260,
        400
      ],
      "credentials": {
        "redditOAuth2Api": {
          "id": "KnPW2HNGMYje2G0S",
          "name": "Reddit account"
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