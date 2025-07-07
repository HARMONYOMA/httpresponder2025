# HTTP Responder Azure Function

This project is an HTTP-triggered Azure Function built with JavaScript, secured using API keys, and automatically deployed to Azure using GitHub Actions.

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
``` 

## 🛠️ Technologies Used
- Azure Functions (JavaScript).
- Node.js 20.
- GitHub Actions (CI/CD pipeline).
- Azure CLI


## 📂 Setup Instructions
✅ Prerequisites
	
- Azure account with an existing Function App.
- Azure Functions Core Tools installed.
- Node.js v20 installed.

🔧 Run Locally
- Start the function locally:
```bash
    func start
```

## 🚀 CI/CD Deployment
The GitHub Actions workflow automatically deploys the Azure Function whenever you push to the main branch.

Workflow Steps:
- Runs on push to the main branch.
- Builds the project using Node.js 18.
- Authenticates to Azure using OIDC (Managed Identity).
- Deploys the Azure Function to the configured Function App.

## 🔑 API Key Security
The function is secured using API keys.

Access Format:
``` text
https://<YOUR_FUNCTION_APP_NAME>.azurewebsites.net/api/<YOUR_FUNCTION_NAME>?code=<YOUR_API_KEY>
``` 
Get API Key:

1.	Go to Azure Portal > Function App > Functions > Your Function > Function Keys.
2. Copy the default or custom key.
 
## 📈 Monitoring
• Integrated with Application Insights for live metrics, request tracking, and failure alerts.

## 📚 Useful Commands
- Run locally
``` bash
func start
```
- Manual deployment (if needed)
``` bash
func azure functionapp publish <YOUR_FUNCTION_APP_NAME> --javascript
```
- Install dependencies
``` bash
npm install
``` 
## ✨ Features
	•	Automated deployments via GitHub Actions.
	•	Simple setup with Azure CLI.
	•	API key security to restrict function access.
	•	Easy local development and testing.

## 🙌 Contribution
If you'd like to contribute, please fork the repository, create a feature branch, and open a pull request.

## 📄 License
This project is licensed under the MIT License.



