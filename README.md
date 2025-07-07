# HTTP Responder Azure Function

This project is an HTTP-triggered Azure Function built with JavaScript, secured using API keys, and automatically deployed to Azure using GitHub Actions.

## 🚀 Project Overview
- **Trigger Type:** HTTP
- **Runtime:** Node.js 20
- **Deployment:** Automated via GitHub Actions
- **Authentication:** API Key (Function Level)

## 📂 Project Structure
```text
httpresponder2025/
│
├── HttpResponder/           # Azure Function code
│   ├── function.json        # Function configuration (auth level)
│   └── index.js             # JavaScript function logic
│
├── host.json                # Host configuration
├── local.settings.json      # Local environment settings (not pushed to GitHub)
└── README.md                # Project documentation
⚙️ Deployment Workflow
This project uses GitHub Actions for Continuous Deployment.
Workflow Summary:
Runs on push to the main branch.
Builds the project using Node.js 18.
Authenticates to Azure using OIDC (Managed Identity).
Deploys the Azure Function to the configured Function App.
✅ API Usage
Endpoint:
https://httpresponder2025.azurewebsites.net/api/HttpResponder?name=YourName&code=YourFunctionKey
Parameters:
name: Your name (required)
code: The API key (required)
Example:
https://httpresponder2025.azurewebsites.net/api/HttpResponder?name=Paschaline&code=YOUR_API_KEY
🔐 Security
API Key Protection: Unauthorized requests will receive a 401 Unauthorized response.
GitHub OIDC Authentication: Secure deployment using Managed Identity.
📈 Monitoring
Integrated with Application Insights for live metrics, request tracking, and failure alerts.
��‍💻 Author
Paschaline Anigbogu

