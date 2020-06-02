# AKS cluster Creation pipeline

This pipeline will create AKS cluster. 
## Pre requisite:
The following pipelines are executed:
- Vnet Creation pipeline
- ACR creation pipeline
- This pipeline requires the following 2 parameters:
  - Resource Group Name
  - Azure Resource group service connection name

Note: Some Parameters still have to be externalized

## Step 1: Create Azure service account, which is used to create AKS cluster
```
$ az login
## Note the Azure subscription id after login

$ az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/<<azure_subscription_id>>"
## Securely store the output from above command. Note the 'appId' and 'password'
```

## Step 2: Add the client ID and secret to the pipeline variables

## Step 3: Execute the pipeline

 