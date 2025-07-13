docs：https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-base.httprequest/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=n8n-nodes-base.httpRequest

json:

```
{
  "nodes": [
    {
      "parameters": {
        "method": "POST",
        "url": "http://156.254.6.45:3002/v1/scrape",
        "sendHeaders": true,
        "headerParameters": {
          "parameters": [
            {
              "name": "Content-Type",
              "value": "application/json"
            }
          ]
        },
        "sendBody": true,
        "specifyBody": "json",
        "jsonBody": "={\n  \"url\": \"{{ $json.url }}\",\n  \"formats\": [\"json\", \"markdown\", \"rawHtml\", \"links\"],\n  \"excludeTags\": [\"iframe\", \"nav\", \"header\", \"footer\"],\n  \"onlyMainContent\": true,\n  \"jsonOptions\": {\n    \"prompt\": \"Identify the main content of the text (i.e., the article or newsletter body). Provide the exact text for that main content verbatim, without summarizing or rewriting any part of it. Exclude all non-essential elements such as banners, headers, footers, calls to action, ads, or purely navigational text. Format this output as markdown using appropriate '#' characters as heading levels. Exclude any promotional or sponsored content on your output. Additionally, you must identify and extract the image urls within this main content. These images must be inside the main content of the page so you must exclude small logo images, icons, avatars and other images which aren't a core part of the main content. The images you extract should at least have a width of 600 pixels (px) so it can be included on our content.\",\n    \"schema\": {\n    \"type\": \"object\",\n      \"properties\": {\n        \"content\": {\n          \"type\": \"string\",\n          \"description\": \"The exact verbatim main text content of the web page in markdown format.\"\n        },\n        \"main_content_image_urls\": {\n          \"type\": \"array\",\n          \"items\": {\n            \"type\": \"string\",\n            \"description\": \"An image url that appears within the main content of the web page. This image must be inside the main content of the page so you must exclude small logo images, icons, avatars and other images which aren't a core part of the main content. The image should be at least 600px in width.\"\n          },\n          \"description\": \"An array of the exact image urls that appear within the main content of the web page. Extra images such as icons and images not relevant to the main content MUST be excluded.\"\n        }\n      },\n      \"required\": [\"content\", \"main_content_image_urls\"]\n    }\n  }\n}",
        "options": {}
      },
      "type": "n8n-nodes-base.httpRequest",
      "typeVersion": 4.2,
      "position": [
        -320,
        -380
      ],
      "id": "bcb9f7fe-7e04-4049-949a-eefe6f1b2413",
      "name": "scrape_url",
      "retryOnFail": true,
      "maxTries": 3,
      "waitBetweenTries": 5000,
      "onError": "continueRegularOutput"
    }
  ],
  "connections": {},
  "pinData": {},
  "meta": {
    "instanceId": "c18b83340b516ec35503d90265d11efa191837c0f100386c72a196f9f7c5c10f"
  }
}
```