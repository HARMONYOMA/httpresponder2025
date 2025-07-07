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

# 🚀 How to Deploy This Project to Your Azure Subscription
Follow these steps to deploy this Azure Function to your own Azure environment.
✅ Prerequisites
- An active Azure account.
- Azure CLI installed.
- Azure Functions Core Tools installed.
- Node.js v20 installed.
- A GitHub account.

## 📂 Steps to Deploy
1️⃣ Clone the Repository
``` bash
git clone https://github.com/<your-username>/httpresponder2025.git
cd httpresponder2025
``` 
2️⃣ Create Required Azure Resources
``` bash
# Create a Resource Group
az group create --name myResourceGroup --location westeurope

# Create a Storage Account (must be globally unique)
az storage account create --name mystoragepaschaline --location westeurope --resource-group myResourceGroup --sku Standard_LRS

# Create the Function App
az functionapp create \
  --resource-group myResourceGroup \
  --consumption-plan-location westeurope \
  --runtime node \
  --runtime-version 20 \
  --functions-version 4 \
  --name <your-functionapp-name> \
  --storage-account mystoragepaschaline \
  --os-type Linux
  ``` 
⚡ Note: Replace "your-functionapp-name" with a unique name.

3️⃣ Configure Deployment Center in Azure
- Go to Azure Portal > Your Function App > Deployment Center.
- Connect your GitHub repository.
- Select your workflow file or let Azure generate a new one.
- Use OIDC Authentication (recommended).
- Complete the setup and Azure will automatically configure your CI/CD.

4️⃣ Set Up API Key Security
- Go to Azure Portal > Function App > Functions > Your Function > Function Keys.
- Copy the function key for API access.

5️⃣ Test Your API

Use the following format:
``` text
https://<your-functionapp-name>.azurewebsites.net/api/HttpResponder?name=YourName&code=<your-api-key>
``` 
Example:
``` text
https://myfunctionapp2025.azurewebsites.net/api/HttpResponder?name=Paschaline&code=abcd1234examplekey
``` 
6️⃣ Optional: Set Up Monitoring
- Go to Application Insights linked to your Function App.
- Configure alerts for failures, performance, and availability.
- Optionally, create an availability test to monitor the API heal

## ✨ Deployment Notes
- This project uses OIDC Authentication with GitHub Actions for secure deployments.
- Make sure your GitHub repository is properly linked to your Azure Function App in the Deployment Center.
- You can customize the GitHub Actions workflow to add build/test steps if needed.

## 🚨 Project Status
The live Azure Function App originally associated with this repository may have been deleted.
To use this project, clone it and redeploy it to your own Azure subscription by following the steps above.


