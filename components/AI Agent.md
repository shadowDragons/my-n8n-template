docs:https://docs.n8n.io/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain.agent/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=%40n8n%2Fn8n-nodes-langchain.agent

json:

```
{
  "nodes": [
    {
      "parameters": {
        "promptType": "define",
        "text": "=你是一个工具推荐中文写作博主，你需要分析工具链接：{{ $json[\"工具连接\"] }}，写一篇推荐该工具的中文博客文章，输出内容如下：\n类型type：Post（固定值）\n状态status: Published（固定值）\n输出标题title(格式：产品名称：一句话总结)，\n摘要summary，\n内容connent，\n日期date：{{$today}}，\n标签tags：多个值，在这里面选（付费，免费，开源，AI），\n分类category：单个值，在这里面选（开发工具，学习教育，数据分析，新闻资讯，设计创意，音视频资源和处理，营销工具，健康科学，职场面试，生活旅行，文化历史，休闲娱乐，文件处理工具，图像资源和处理，搜索百科）\nurl：{{ $json[\"工具连接\"] }}\nslug(产品名称英文或者拼音)",
        "hasOutputParser": true,
        "options": {
          "systemMessage": ""
        }
      },
      "type": "@n8n/n8n-nodes-langchain.agent",
      "typeVersion": 1.8,
      "position": [
        -320,
        -160
      ],
      "id": "2d53f9e8-7ff7-42a9-af1a-3abf935e6f9e",
      "name": "AI Agent"
    },
    {
      "parameters": {
        "jsonSchemaExample": "{\n\t\"title\": \"title\",\n\t\"summary\": \"summary\",\n    \"content\": \"content\",\n    \"url\": \"url\",\n    \"category\": \"category\",\n    \"date\": \"date\",\n    \"type\": \"Post\",\n    \"statuts\": \"Published\",\n    \"slug\": \"slug\",\n    \"tags\": [\"tag1\", \"tag2\"]\n}"
      },
      "type": "@n8n/n8n-nodes-langchain.outputParserStructured",
      "typeVersion": 1.2,
      "position": [
        -160,
        20
      ],
      "id": "42731d58-b63b-4120-8949-b4f4d311ea24",
      "name": "Structured Output Parser"
    },
    {
      "parameters": {
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.lmChatDeepSeek",
      "typeVersion": 1,
      "position": [
        -320,
        0
      ],
      "id": "72e809da-0205-41ef-8dc8-e53ac4a5f6d4",
      "name": "DeepSeek Chat Model",
      "credentials": {
        "deepSeekApi": {
          "id": "HG2MiMSzHpKDJXkh",
          "name": "DeepSeek account"
        }
      }
    }
  ],
  "connections": {
    "Structured Output Parser": {
      "ai_outputParser": [
        [
          {
            "node": "AI Agent",
            "type": "ai_outputParser",
            "index": 0
          }
        ]
      ]
    },
    "DeepSeek Chat Model": {
      "ai_languageModel": [
        [
          {
            "node": "AI Agent",
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