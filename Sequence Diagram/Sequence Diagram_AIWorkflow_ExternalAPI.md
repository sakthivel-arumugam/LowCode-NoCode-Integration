```mermaid
sequenceDiagram
    participant AI_Workflow as AI Workflow
    participant Power_Platform as Power Platform Workflow
    participant HTTP_Connector as HTTP Connector
    participant External_API as External API

    AI_Workflow->>+Power_Platform: Trigger workflow
    Power_Platform->>+HTTP_Connector: Send request
    HTTP_Connector->>+External_API: Call external API
    External_API-->>+HTTP_Connector: Send response via webhook
    HTTP_Connector-->>+Power_Platform: Forward response
    Power_Platform-->>-AI_Workflow: Notify response received
```
