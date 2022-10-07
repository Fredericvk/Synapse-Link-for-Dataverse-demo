# Synapse-Link-for-Dataverse-demo

## Goal
The goal of this easily set up a demo environment with Synapse Link for dataverse, combining sample data in dataverse and generated data simulating Outlook interactions with customers.

## Architecture overview:
![Demo scenario](https://github.com/Fredericvk/Synapse-Link-for-Dataverse-demo/blob/main/Architecture/Demo%20Scenario.png)  
In this scenario, the Outlook interactions are generated through a Spark notebook.

## Prerequisites
- Azure tenant with a subscription with owner rights

## Steps
1. Spin up a Microsoft Dataverse database with sample data.  
**Instructions:** https://learn.microsoft.com/en-us/power-platform/admin/create-database

2. Create a Synapse workspace in the SAME tenant and region as your Dataverse instance.  
**Instructions:** https://learn.microsoft.com/en-us/azure/synapse-analytics/quickstart-create-workspace

3. Set up Synapse Link for Dataverse. Here you can all the tables you land in Synapse, but make sure to select the Account table. Also make sure to enable "connect to Synapse workspace".  
**Instructions:** https://learn.microsoft.com/en-us/power-apps/maker/data-platform/azure-synapse-link-synapse

4. Import the two notebooks in your Synapse workspace.  
**Instructions:** https://learn.microsoft.com/en-us/azure/synapse-analytics/spark/apache-spark-development-using-notebooks#create-a-notebook

5. Run first the Generate - Interactions notebook. Once that is completed, run the Create Table Acc Int notebook.  
**Note:** Make sure that in the notebooks, you change the lake database that is being used. You can find the name of yours in the details tab Synapse Link for Dataverse in the PowerApps portal https://make.powerapps.com
  
6. Create a Power BI report based off the created Table Acc Int.  
**Instructions on how to connect your Power BI workspace to your Azure Synapse Analytics workspace::** https://learn.microsoft.com/en-us/azure/synapse-analytics/quickstart-power-bi
