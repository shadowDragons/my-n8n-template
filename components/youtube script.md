{
  "nodes": [
    {
      "parameters": {
        "jsCode": "const extractYoutubeId = (url) => {\n  // Regex pattern that matches both youtu.be and youtube.com URLs\n  const pattern = /(?:youtube\\.com\\/(?:[^\\/]+\\/.+\\/|(?:v|e(?:mbed)?)\\/|.*[?&]v=)|youtu\\.be\\/)([^\"&?\\/\\s]{11})/;\n  const match = url.match(pattern);\n  return match ? match[1] : null;\n};\n\n// Input URL from previous node\nconst youtubeUrl = $input.first().json.url; // Adjust this based on your workflow\n\n// Process the URL and return the video ID\nreturn [{\n  json: {\n    videoId: extractYoutubeId(youtubeUrl)\n  }\n}];\n"
      },
      "id": "46306683-71ca-4d33-80bc-221dd18a4199",
      "name": "YouTube Video ID",
      "type": "n8n-nodes-base.code",
      "position": [
        860,
        540
      ],
      "typeVersion": 2
    },
    {
      "parameters": {
        "resource": "video",
        "operation": "get",
        "videoId": "={{ $json.videoId }}",
        "options": {}
      },
      "id": "b4bb759c-e9e9-4a5a-9ad5-2f98cf9a066f",
      "name": "Get YouTube Video",
      "type": "n8n-nodes-base.youTube",
      "position": [
        1060,
        540
      ],
      "typeVersion": 1,
      "credentials": {
        "youTubeOAuth2Api": {
          "id": "B1VIBsl4dcbZLcRc",
          "name": "YouTube account"
        }
      }
    },
    {
      "parameters": {
        "assignments": {
          "assignments": [
            {
              "id": "7653a859-556d-4e00-bafa-6f70f90de0d7",
              "name": "transcript",
              "type": "string",
              "value": "={{ $json.cleanedTranscript }}"
            }
          ]
        },
        "options": {}
      },
      "id": "7eb5ad28-75ca-40c8-94dc-49f45ddc9ce8",
      "name": "cleanedTranscript",
      "type": "n8n-nodes-base.set",
      "position": [
        1620,
        540
      ],
      "typeVersion": 3.4
    },
    {
      "parameters": {
        "functionCode": "// Extract and process the transcript\nconst data = $input.first().json;\n\nif (!data.transcript && !data.text) {\n  return {\n    json: {\n      success: false,\n      message: 'No transcript available for this video',\n      videoUrl: $input.first().json.body?.videoUrl || 'Unknown'\n    }\n  };\n}\n\n// Process the transcript text\nlet transcriptText = '';\n\n// Handle different API response formats\nif (data.transcript) {\n  // Format for array of transcript segments\n  if (Array.isArray(data.transcript)) {\n    data.transcript.forEach(segment => {\n      if (segment.text) {\n        transcriptText += segment.text + ' ';\n      }\n    });\n  } else if (typeof data.transcript === 'string') {\n    transcriptText = data.transcript;\n  }\n} else if (data.text) {\n  // Format for single transcript object with text property\n  transcriptText = data.text;\n}\n\n// Clean up the transcript (remove extra spaces, normalize punctuation)\nconst cleanedTranscript = transcriptText\n  .replace(/\\s+/g, ' ')\n  .replace(/\\s([.,!?])/g, '$1')\n  .trim();\n\nreturn {\n  json: {\n    success: true,\n    videoUrl: $input.first().json.body?.videoUrl || 'From transcript',\n    rawTranscript: data.text || data.transcript,\n    cleanedTranscript,\n    duration: data.duration,\n    offset: data.offset,\n    language: data.lang\n  }\n};"
      },
      "id": "929032cf-1a2e-490c-9ddf-6b0ed46e0d11",
      "name": "processTranscript",
      "type": "n8n-nodes-base.function",
      "position": [
        1440,
        540
      ],
      "typeVersion": 1
    },
    {
      "parameters": {
        "url": "https://youtube-transcript3.p.rapidapi.com/api/transcript",
        "sendQuery": true,
        "queryParameters": {
          "parameters": [
            {
              "name": "videoId",
              "value": "={{ $json.id }}"
            }
          ]
        },
        "sendHeaders": true,
        "headerParameters": {
          "parameters": [
            {
              "name": "x-rapidapi-host",
              "value": "youtube-transcript3.p.rapidapi.com"
            },
            {
              "name": "x-rapidapi-key",
              "value": "5230d7b76fmsheb407ac6cb96efap1c703cjsnd3f8f5715b27"
            },
            {
              "name": "Content-Type",
              "value": "application/json"
            }
          ]
        },
        "options": {}
      },
      "id": "221729c1-c9c6-4c52-bcb1-df518e01fced",
      "name": "extractTranscript",
      "type": "n8n-nodes-base.httpRequest",
      "position": [
        1240,
        540
      ],
      "typeVersion": 3
    },
    {
      "parameters": {
        "formTitle": "Toutube",
        "formFields": {
          "values": [
            {
              "fieldLabel": "url",
              "requiredField": true
            }
          ]
        },
        "options": {}
      },
      "type": "n8n-nodes-base.formTrigger",
      "typeVersion": 2.2,
      "position": [
        640,
        540
      ],
      "id": "65092322-a51a-4511-bae9-931139bafa49",
      "name": "On form submission",
      "webhookId": "efe304c0-8666-42d7-87ed-8804c0c14570"
    }
  ],
  "connections": {
    "YouTube Video ID": {
      "main": [
        [
          {
            "node": "Get YouTube Video",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "Get YouTube Video": {
      "main": [
        [
          {
            "node": "extractTranscript",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "processTranscript": {
      "main": [
        [
          {
            "node": "cleanedTranscript",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "extractTranscript": {
      "main": [
        [
          {
            "node": "processTranscript",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "On form submission": {
      "main": [
        [
          {
            "node": "YouTube Video ID",
            "type": "main",
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