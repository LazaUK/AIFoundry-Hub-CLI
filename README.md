# Azure AI Studio: Creating Hub resource with Azure CLI
This repo explains how to use the **_Command Line Interface (CLI)_** to create Azure AI Studio _hub_ resource. It shows not only how to deploy Hub with auto-generated dependant resources like Azure Storage and Azure Key Vault, but also how to create a new Hub and integrate it with already existing Storage and Key Vault.

> [!WARNING]
> You can create Azure AI Studio hub with existing Azure Storage account only if:
> - The Storage account uses _Standard_ performance tier, not _Premium_,
> - Both _Blob_ and _File_ service capabilities are enabled,
> - If storage is of _Azure Data Lake Storage_ type, then its _Hierarchical namespace_ feature is disabled.

## Table of contents:
- [Pre-requisites](https://github.com/LazaUK/AIStudio-Hub-CLI#pre-requisites)
- [Scenario 1: Hub creation with bare minimum configuration](https://github.com/LazaUK/AIStudio-Hub-CLI#scenario-1-hub-creation-with-bare-minimum-configuration)
- [Scenario 2: Hub creation with existing dependant resources - CLI flags]()
- [Scenario 3: Hub creation with existing dependant resources - YAML config]()

## Pre-requisites
1. To build this demo, you'll need:
    - An Azure subscription with an active Entra ID account,
    - An Azure Storage account (for Scenario 2 and 3),
    - An Azure Key Vault (for Scenario 2 and 3).
2. Use the ```az login``` command to authenticate with your Azure subscription using your Entra ID credentials.

## Scenario 1: Hub creation with bare minimum configuration

## Scenario 2: Hub creation with existing dependant resources - CLI flags

## Scenario 3: Hub creation with existing dependant resources - YAML config
