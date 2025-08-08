# PROG8860 Assignment 3 - Jenkins CI/CD Pipeline for Azure Functions

**Student Name**: Keerthana Garimella  
**Student ID**: 8985513  
**Course**: PROG8860-S25-CICD  
**Assignment**: Assignment 3 - Jenkins CI/CD Pipeline for Azure Function

---

## 📋 Project Overview

This project demonstrates a complete Jenkins CI/CD pipeline that automatically builds, tests, and deploys an Azure Functions application. The pipeline integrates with GitHub for source code management and deploys to Microsoft Azure.

---

## 🎯 Assignment Objectives Met

✅ Build, Test, and Deploy stages functioning correctly  
✅ At least 3 comprehensive test cases 
✅ Azure Functions integration  
✅ Automated CI/CD pipeline with Jenkins  
✅ GitHub repository integration  

---

## 🏗️ Architecture Overview

GitHub Repository → Jenkins Pipeline → Azure Functions  
↓                            ↓                        ↓  
Source Code         Build → Test →    Deployed  
Management           Deploy Stages   Application

---

## 💻 Technology Stack

- **Runtime**: Node.js 18  
- **Cloud Platform**: Microsoft Azure Functions v4  
- **CI/CD Tool**: Jenkins  
- **Testing Framework**: Jest  
- **Source Control**: GitHub  
- **Authentication**: Azure Service Principal  

---

## 🚀 Azure Function Details

### Function Specifications
- **Function Name**: HelloWorld  
- **HTTP Methods**: GET, POST  
- **Authentication**: Anonymous  
- **Runtime**: Node.js 18  
- **Azure Functions Version**: v4 (Latest)

### Azure Resources
- **Resource Group**: my-azure-functiondemo_group-b294  
- **Function App**: my-azure-functiondemo  
- **Region**: Central Canada

### Function Endpoints
- **Base URL**:  
  `https://my-azure-functiondemo.azurewebsites.net/api/HelloWorld`

- **With Parameter**:  
  `https://my-azure-functiondemo.azurewebsites.net/api/HelloWorld?name=YourName`

---

## 🧪 Testing Strategy

### Test Coverage
The application includes comprehensive test cases covering:

- Basic Functionality Test – Validates default "Hello, World!" response  
- HTTP Response Validation – Ensures successful response structure  
- Query Parameter Handling – Tests custom name parameter functionality  
- Edge Case Testing – Handles empty name parameters  
- Logging Verification – Confirms proper request logging  
- Multiple Name Scenarios – Tests various input combinations

### Test Results

✅ Test Suites: 1 passed, 1 total  
✅ Tests: 6 passed, 6 total  
⏱️ Time: ~0.8s  

---

## 🔄 Jenkins CI/CD Pipeline

### Pipeline Stages

#### 1. Build Stage 🔧
- Cleans previous build artifacts  
- Installs npm dependencies  
- Prepares the application for testing  

#### 2. Test Stage 🧪
- Executes Jest test suite  
- Validates all test cases  

#### 3. Deploy Stage 🚀
- Authenticates with Azure using Service Principal  
- Packages application  
- Deploys using ZIP method  
- Configures app settings  

---

## 🌐 Live Application

### Deployment Verification

The function is deployed and accessible at:

- `https://my-azure-functiondemo.azurewebsites.net/api/HelloWorld`

### Testing the Live Function

#### Basic Request:

```http
GET https://my-azure-functiondemo.azurewebsites.net/api/HelloWorld
Response: Hello, World!

With Custom Name:
http
GET https://my-azure-functiondemo.azurewebsites.net/api/HelloWorld?name=Keerthana
Response: Hello, Keerthana!

📁 Project Structure

PROG8860-S25-CICD/
├── src/
│   └── functions/
│       └── HelloWorld.js
├── tests/
│   └── hello-world.test.js
├── screenshots/
│   ├── build.png
│   ├── test.png
│   ├── deploy.png
│   └── sample-app.png
├── Jenkinsfile
├── package.json
├── host.json
├── jest.config.js
└── README.md

⚙️ Setup and Configuration
Prerequisites
Jenkins server with Azure CLI

Azure subscription + Service Principal

GitHub repository access

Node.js 18+

Jenkins Credentials Required
azure-subscription-id

azure-tenant-id

azure-client-id

azure-client-secret

Local Development
bash
# Clone repository
git clone https://github.com/KeerthanaGarimella/PROG8860-S25-CICD.git

# Install dependencies
npm install

# Run tests
npm test

# Run locally
func start
