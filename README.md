# Synapse Sandbox
Deploy a Self-Service Analytics Sandbox in Azure Synapse Analytics

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FArvind-Microsoft%2FISD_Synapse_Sandbox%2Fmain%2FSynapse_sandbox_template.json)

## Architecture
![image](https://user-images.githubusercontent.com/106280297/195119368-61c6135f-0058-4113-a09e-05ba707d7b8d.png)

Diagram above shows the overall architecture of Synapse workspace - this small project deploys the required infrstructure to try Synapse workspace with minimum product specifications

## Components that are deployed on this process
- Storage Account
  - Storage Account Container
  - Storage Account Contributor Role
- Synapse Workspace
  - Dedicate SQL Pool
  - Apache Spark Pool
- Logic App

## Pre-Requisites
- Azure Account
  - Azure Subscription level permission with Contributor Role or any other administrator role to deploy the resources and add access controls (IAM) if a new Resource   Group is created
  - Or access to a resource group for which you are assigned as the Owner role
- Visual Studio Code access to change/modify the code according to the test environment standard

## Template Deployment
The template deployment requires 3 letter acronym, using that provided 3 letter acronym all the required resources are created automatically 

## Storage Account and Container in Portal
![image](https://user-images.githubusercontent.com/106280297/195117834-fb0be954-3dfa-4fe0-aa99-934c3f30818b.png)

## Synapse Workspace
![image](https://user-images.githubusercontent.com/106280297/195118251-f5d80059-4796-4216-a736-74b1b9e3f066.png)

#### Resource Properties
- Storage Account and File system are created before this Synapse workspace
- “Default” Managed Virtual Network is used
- All the Ip address are allowed to access the workspace for Demo purpose. DO NOT use this for Production environment

## Dedicated SQL and Apache Spark Pool
![image](https://user-images.githubusercontent.com/106280297/195118913-01e776d9-ed52-492d-9e4e-89d0b11ac2ff.png)

## Logic App
![image](https://user-images.githubusercontent.com/106280297/195119104-54b0ea14-316a-47a6-8d79-c1327c5ff3bb.png)

#### Resource Properties
- Purpose of the Logic App is to execute and stops dedicated SQL Pool everyday
- It is designed to run everyday at 5 PM EST
- Note - status of the Logic App will change to fail state for that day when the dedicated SQL pool is already turned off


# Decommission  

Please deleted the created resource group which was specified during the creation process
Note: Individual resources are required to be deleted if an existing Resource Group was selected during the creation process

![image](https://user-images.githubusercontent.com/106280297/195122091-ee9cf079-e95e-40b1-b13e-e3fcd13ca38b.png)

![image](https://user-images.githubusercontent.com/106280297/195120459-e73388e0-8edc-43e8-8993-567cd7848fac.png)

_ManagedRG will be deleted automatically when the main resource group is deleted

