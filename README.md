
## Power BI Embedded Single Page Application (SPA)

This implementation demonstrates how to embed Power BI reports in a web application
using the Microsoft Authentication Library (MSAL) Browser library for authentication
and the Power BI JavaScript SDK for embedding functionality.

## Prerequisites

### Azure AD (Entra ID) App Registration Setup

1. **Create App Registration**:
   - Navigate to Azure Portal > Azure Active Directory > App registrations
   - Click "New registration"
   - Provide a name for your application
   - Select "Accounts in this organizational directory only" for supported account types
   - Set Redirect URI type to "Single-page application (SPA)" 
   - Add your application's redirect URI (e.g., http://localhost:3000)

2. **API Permissions**:
   - Add delegated permissions for Power BI Service:
     - Report.Read.All
     - Dataset.Read.All

3. **Power BI Service Configuration**:
   - Ensure the user has access to Power BI workspace
   - Configure Power BI tenant settings to allow embedding

## Required Dependencies
- From CDN: @azure/msal-browser - For Azure AD authentication
- From node_modules: powerbi-client - Power BI JavaScript SDK for embedding

```
npm install
```

## Setup

To embed the report, you need to configure four essential variables in the `lab.js` file:

```javascript
tenantId: "tenant-id",
clientId: "app-registration-cleint-id",
reportId: "power-bi-report-id",
userUpn: "user-upn",
```
## Run
Use a web server to host single-page-report.html and lab.js in the same folder

For example:
1. Start server on port 3000
2. Open http://localhost:3000/single-page-report.html

## Lab
Use lab.json for add custom code to implement:
 - pipeConfig: any changes to the embed config before embedding
 - bind: any code to run after embedding. e.g subscribe to report events
