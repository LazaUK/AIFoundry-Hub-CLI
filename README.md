# Azure AI Studio: Creating Hub resource with Azure CLI
This repo explains how to use the **_Command Line Interface (CLI)_** to create Azure AI Studio _hub_ resource. It shows not only how to deploy Hub with auto-generated dependant resources like Azure Storage and Azure Key Vault, but also how to create a new Hub and integrate it with already existing Storage and Key Vault.

> [!WARNING]
> You can create Azure AI Studio hub with an existing Azure Storage account only if:
> - The Storage account uses _Standard_ performance tier, not _Premium_,
> - Both _Blob_ and _File_ service capabilities are enabled,
> - If storage is of _Azure Data Lake Storage_ type, then its _Hierarchical namespace_ feature is disabled.

## Table of contents:
- [Pre-requisites](https://github.com/LazaUK/AIStudio-Hub-CLI#pre-requisites)
- [Scenario 1: Hub creation with bare minimum configuration](https://github.com/LazaUK/AIStudio-Hub-CLI#scenario-1-hub-creation-with-bare-minimum-configuration)
- [Scenario 2: Hub creation with existing dependant resources - CLI flags](https://github.com/LazaUK/AIStudio-Hub-CLI#scenario-2-hub-creation-with-existing-dependant-resources---cli-flags)
- [Scenario 3: Hub creation with existing dependant resources - YAML config](https://github.com/LazaUK/AIStudio-Hub-CLI#scenario-3-hub-creation-with-existing-dependant-resources---yaml-config)

## Pre-requisites
1. To build this demo, you'll need:
    - An Azure subscription with an active Entra ID account,
    - An Azure Storage account (for Scenario 2 and 3),
    - An Azure Key Vault (for Scenario 2 and 3).
2. Use the ```az login``` command to authenticate with your Azure subscription using your Entra ID credentials.

## Scenario 1: Hub creation with bare minimum configuration
1. You can create Azure AI Studio hub with the following Az CLI command by providing values for 2 mandatory parameters only: **Resource Group** and **Hub** name:
``` PowerShell
az ml workspace create --kind hub --resource-group <RESOURCE_GROUP_NAME> --name <AI_HUB_NAME>
```
2. As no other details are provided, Azure will auto-provision dependant **Azure Storage** and **Azure Key Vault** resources.

## Scenario 2: Hub creation with existing dependant resources - CLI flags
1. If you already have an existing **Azure Storage** account, you can retrieve its Resource ID either from Azure portal, or by existing the following Az CLI command:
``` PowerShell
az storage account show --name <STORAGE_NAME> --query "id"
```
> [!Note]
> returned Resource ID should be in this format: _/subscriptions/<SUBSCRIPTION_ID>/resourceGroups/<RESOURCE_GROUP>/providers/Microsoft.Storage/storageAccounts/<STORAGE_ACCOUNT>_
2. If you already have an existing **Azure Kay Vault**, you can retrieve its Resource ID either from Azure portal, or by existing the following Az CLI command:
``` PowerShell
az keyvault show --name <KEYVAULT_NAME> --query "id"
```
> [!Note]
> returned Resource ID should be in this format: _/subscriptions/<SUBSCRIPTION_ID>/resourceGroups/<RESOURCE_GROUP>/providers/Microsoft.KeyVault/vaults/<KEY_VAULT>_
3. You can pass Resource IDs from the above steps to use existing Storage and Key Vault as default dependant resources for the new Hub resource in the following Az CLI command:
``` PowerShell
az ml workspace create --kind hub --resource-group <RESOURCE_GROUP_NAME> --name <HUB_NAME> --display-name <HUB_DISPLAY_NAME> --description <HUB_DESCRIPTION> --location <HUB_AZURE_REGION> --storage-account <STORAGE_RESOURCE_ID> --key-vault <KEYVAULT_RESOURCE_ID>
```

## Scenario 3: Hub creation with existing dependant resources - YAML config
