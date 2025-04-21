**1. HTTP Triggered Flows (AI workflow → Power Automate HTTP trigger)**

**Scenario:**
- FastAPI sends an HTTP request to a Power Automate flow when a document is processed.
- Power Automate validates the document, stores metadata, and triggers further workflows.

- Example:- FastAPI calls https://powerautomate.com/validate-document
- Power Automate checks the document and returns a response.

**2. Webhook Driven AI (Power Automate → AI workflow API)**

**Scenario:**
- Power Automate sends a webhook request to FastAPI when an event occurs (e.g., new document uploaded).
- FastAPI processes the document and returns results asynchronously.

- Example:- Power Automate triggers a webhook: POST https://fastapi.com/process-document
- FastAPI processes and responds with validation results.

**3. Asynchronous Queues (Service Bus for Long-Running Tasks)**

**Scenario:**
- FastAPI sends tasks to Azure Service Bus for long-running document processing.
- Power Automate listens to the queue and processes tasks asynchronously.

- Example:- FastAPI sends a message to Azure Service Bus Queue
- Power Automate picks up the message and triggers validation.

**4. Custom Connectors (Native Drag-and-Drop Actions in NoCode)**

**Scenario:**
- A custom connector allows Power Automate users to interact with FastAPI without writing code.
- Users can drag-and-drop actions like "Validate Document" or "Get AI Feedback."

- Example:- Power Automate has a "Process Document" action that calls FastAPI.
- Users configure it without needing API knowledge.
