# Sequence Diagram: AI Workflow and Power Automate workflow integration via Power Platform

```mermaid
sequenceDiagram
    participant AI as AI Workflow
    participant CC as Custom Connector
    participant PP as Power Platform Workflow
    participant DV as Dataverse (Optional)

    AI->>CC: HTTP POST (Webhook URL)
    CC->>PP: Trigger Workflow
    PP-->>PP: Execute Workflow Actions
    PP-->>DV: Save Response (Optional)
    DV-->>PP: Acknowledge Save (Optional)
    PP-->>CC: Workflow Response
    CC-->>AI: Return Response
```

## Description
1. **AI Workflow**:
   - Initiates the process by making an HTTP POST request to the custom connector's webhook URL.

2. **Custom Connector**:
   - Acts as a bridge, triggering the Power Platform workflow upon receiving the HTTP POST request.

3. **Power Platform Workflow**:
   - Executes the defined workflow actions.
   - Optionally saves the response in Dataverse.

4. **Dataverse (Optional)**:
   - Stores the workflow response if required.

5. **Response Handling**:
   - The workflow response is sent back to the custom connector, which forwards it to the AI workflow.

