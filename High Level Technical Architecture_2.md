# High-Level Technical Architecture: Custom API and Power Automate Integration

## Architecture Diagram
The following Mermaid diagram illustrates the integration of custom APIs, custom connectors, and Power Automate workflows:

```mermaid
%%{init: {'theme': 'base', 'themeVariables': {'primaryColor': '#0078D4', 'edgeLabelBackground':'#ffffff', 'tertiaryColor': '#FFB900', 'background':'#ffffff'}}}%%
flowchart TD
    subgraph Custom_API["Custom API (SocGen APIs)"]
        C1[Internal API]
    end

    subgraph Custom_Connector["Custom Connector"]
        CC1[OpenAPI Specification]
        CC2[OAuth 2.0 Authentication]
    end

    subgraph Power_Automate["Power Automate Workflow"]
        PA1[Webhook Trigger]
        PA2[Workflow Actions]
    end

    C1 -->|HTTP POST| PA1
    PA1 -->|Trigger Workflow| CC1
    CC1 -->|Authenticate| CC2
    PA1 --> PA2
    PA2 -->|Perform Actions| C1
```

## Key Components
1. **Custom API (SocGen APIs)**:
   - Internal APIs that trigger workflows by making HTTP POST requests to Power Automate webhook endpoints.

2. **Custom Connector**:
   - Built using OpenAPI specifications.
   - Secured with OAuth 2.0 authentication.

3. **Power Automate Workflow**:
   - Starts with a webhook trigger when an internal API sends a request.
   - Executes workflow actions such as data processing, notifications, or API calls.

## Benefits
- **Seamless Integration**: Connects internal APIs with Power Automate workflows using custom connectors.
- **Automation**: Enables automated workflows triggered by API calls.
- **Security**: Ensures secure communication with OAuth 2.0 authentication.

