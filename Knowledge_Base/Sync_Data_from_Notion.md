# Sync Data from Notion

AgentBuilder datasets support importing from Notion and setting up **synchronization** so that data updates in Notion are automatically synced to AgentBuilder.

## Authorization Verification

1. When creating a dataset and selecting the data source, click **Sync from Notion Content -- Bind Now** and follow the prompts to complete the authorization verification.
2. Alternatively, you can go to **Settings -- Data Sources -- Add Data Source**, click on the Notion source **Bind**, and complete the authorization verification.

![binding_notion](/Knowledge_Base/images/binding_notion.png)

## Importing Notion Data

After completing the authorization verification, go to the create dataset page, click **Sync from Notion Content**, and select the authorized pages you need to import.

## Segmentation and Cleaning

Next, choose your **segmentation settings** and **indexing method**, then **Save and Process**. Wait for AgentBuilder to process this data for you, which typically requires token consumption in the LLM provider. AgentBuilder supports importing not only standard page types but also aggregates and saves page properties under the database type.

***Please note: Images and files are not currently supported for import, and tabular data will be converted to text display.***

## Synchronizing Notion Data

If your Notion content is modified, you can directly click **Sync** in the AgentBuilder dataset **Document List Page** to perform a one-click data synchronization. This step requires token consumption.

## Integration Configuration Method for Community Edition Notion

Notion integration can be done in two ways: **internal integration** and **public integration**. You can configure them as needed in AgentBuilder. For specific differences between the two integration methods, please refer to [Notion Official Documentation](https://developers.notion.com/docs/authorization). 

## 1. Using Internal Integration

First, create an integration in the integration settings page [Create Integration](https://www.notion.so/my-integrations). By default, all integrations start as internal integrations; internal integrations will be associated with the workspace you choose, so you need to be the workspace owner to create an integration.

Specific steps:

Click the **New integration** button. The type is **Internal** by default (cannot be modified). Select the associated space, enter the integration name, upload a logo, and click **Save** to create the integration successfully.

![create_notion_integration](/Knowledge_Base/images/create_notion_integration.png) 

After creating the integration, you can update its settings as needed under the Capabilities tab and click the **Show** button under Secrets to copy the secrets.

![notion_integration_settings](/Knowledge_Base/images/notion_integration_settings.png) 

After copying, go back to the AgentBuilder source code, and configure the relevant environment variables in the **.env** file. The environment variables are as follows:

**NOTION_INTEGRATION_TYPE**=internal or **NOTION_INTEGRATION_TYPE**=public

**NOTION_INTERNAL_SECRET**=your-internal-secret

## 2. Using Public Integration

**You need to upgrade the internal integration to a public integration**. Navigate to the Basic Information page of the integration, and toggle the switch to make the integration public. When switching to the public setting, you need to fill in additional information in the Organization Information form below, including your company name, website, and redirect URL, then click the Submit button.

![notion_public_integration](/Knowledge_Base/images/notion_public_integration.png) 

After successfully making the integration public on the integration settings page, you will be able to access the integration key in the Keys tab:

![notion_public_integration_key](/Knowledge_Base/images/notion_public_integration_key.png) 

Go back to the AgentBuilder source code, and configure the relevant environment variables in the **.env** file. The environment variables are as follows:

- **NOTION_INTEGRATION_TYPE**=public
- **NOTION_CLIENT_SECRET**=your-client-secret
- **NOTION_CLIENT_ID**=your-client-id

After configuration, you can operate the Notion data import and synchronization functions in the dataset.