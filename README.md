# Azure AI Studio: Creating new Hub resource with Azure command-line interface (CLI) client
This repo explains how to use the **_Command Line Interface (CLI)_** to create Azure AI Studio _hub_ resource. It shows not only how to deploy Hub with auto-generated dependant resources like Azure Storage and Azure Key Vault, but also how to create a new Hub and integrate it with already existing Storage and Key Vault.

> [!NOTE]
> This step-by-step guide assumes that you are using Windows 11 on your development machine.

## Table of contents:
- [Pre-requisites]()
- [Scenario 1: Hub creation with bare minimum configuration]()
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
