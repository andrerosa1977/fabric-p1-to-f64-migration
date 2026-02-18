# SETUP Guide for Service Principal and Migration Configuration

## Introduction
This guide provides step-by-step instructions for creating a Service Principal and configuring the migration for the project.

## Creating a Service Principal
### Step 1: Log in to Azure
1. Go to the [Azure Portal](https://portal.azure.com).
2. Sign in using your Azure account credentials.

### Step 2: Open Cloud Shell
1. Click on the Cloud Shell icon in the top-right corner of the Azure Portal.

### Step 3: Create a Service Principal using Azure CLI
Run the following command in the Cloud Shell:
```bash
az ad sp create-for-rbac --name <Your-Service-Principal-Name> --role contributor --scopes /subscriptions/<Your-Subscription-ID>
```
Replace `<Your-Service-Principal-Name>` with a name you choose, and `<Your-Subscription-ID>` with your actual subscription ID.

### Step 4: Note the Output Details
- **App ID**: This is your Service Principal ID.
- **Password**: Store this securely as it will not be shown again.
- **Tenant ID**: Note this ID for future configurations.

## Configuring the Migration
### Step 1: Set up your environment
Make sure your environment is ready for migration by installing necessary tools and dependencies.

### Step 2: Use the Service Principal Credentials
You will need to use the App ID, Password, and Tenant ID in your migration configurations.

### Step 3: Validate the Configuration
1. Test the Service Principal access by running a simple Azure CLI command like:
```bash
az login --service-principal -u <App-ID> -p <Password> --tenant <Tenant-ID>
```

## Conclusion
Follow these steps to successfully set up a Service Principal and configure the migration. For further assistance, refer to the official Azure documentation or reach out to the support team.