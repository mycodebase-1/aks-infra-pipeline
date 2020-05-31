# Create an Azure Cosmos DB account for Core (SQL) API Using Azure Pipelines

This pipeline will create an Azure Cosmos account for Core (SQL) API, provisioned for single region using ARM Template. The DB account will be exposed only to a dedicated VNet and its subnet.

## Pre requisite:
The pipeline assumes that the existing VNet/Subnet has been created. If not, create it using [vNet Creation](https://github.com/abhishekjawali/aks-pipelines-complete/tree/master/vnet-pipeline) pipeline.


Below are the parameters which should be configured in the parameters file(azuredeploy.parameter.json):

- **Name:** Enter the DB account name to be created.
- **Location:** Enter the Location of account to be created.
- **Virtual Network Name:** Enter the Virtual Network name.
- **Subnet Name:** Enter the subnet name.

Below are the parameters that need to be passed during pipeline execution

- **service_connection:** Service connection used to connect to Azure Portal.
- **subscription_id:** Azure Portal Subscription ID.
- **resource_group:** Name of the Resource Group.
- **location:** Location of the Azure Cosmos DB account (Example: East US)
- **vnet_name:** vNet Name which needs access to Cosmos DB
- **subnet_name:** Subnet Name which should have access to Cosmos DB

Below outputs will be displayed once the pipeline is completed successfully.

- **documentEndpoint** URI of the DB account
- **accountKey** Primary Key of the account created
- **connectionString** URI and its associated Primary Key
