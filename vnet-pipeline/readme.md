# Azure VNet Creation pipeline

This pipeline will create VNet in Azure. This gives us a logical seperation between resources. The resources created within this VNet will be private from other resources.

## Step 1: Create service connection
Service Connection for Azure Resource Manager. Select the resource group. 
Make a note of the service connection name. This is mandatory input when executing the pipeline.

## Step 2: Execute the pipeline
The pipeline at runtime, expects the following parameters:
 - Resource Group Name
 - Service connection name


This will then create a VNet in the selected resource group. 