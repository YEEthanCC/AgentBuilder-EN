# Create Application

You can create applications in AgentBuilder's studio in three ways:

- Create based on an application template (recommended for beginners)
- Create a blank application
- Create application via DSL file (Local/Online)

## Creating an Application from a Template

When using AgentBuilder for the first time, you might be unfamiliar with creating applications. To help new users quickly understand what types of applications can be built on AgentBuilder, the prompt engineers from the AgentBuilder team have already created high-quality application templates for multiple scenarios.

You can select "Studio" from the navigation menu, then choose "Create from Template" in the application list.

![Create_from_template](/Application_Orchestration/images/Create_from_template.png)

Select any template and click **Use this template**.

![templates](/Application_Orchestration/images/templates.png)

## Creating a New Application

If you need to create a blank application on AgentBuilder, you can select "Studio" from the navigation and then choose "Create from Blank" in the application list.

When creating an application for the first time, you might need to first understand the basic concepts of the four different types of applications on AgentBuilder: Chatbot, Text Generator, Agent and Workflow.

![Create_blank_app](/Application_Orchestration/images/Create_blank_app.png)

When selecting a specific application type, you can customize it by providing a name, choosing an appropriate icon(or uploading your favorite image as an icon), and writing a clear and concise description of its purpose. These details will help team members easily understand and use the application in the future.

## Creating from a DSL File

AgentBuilder DSL is an AI application engineering file standard defined by AgentBuilder.AI. The file format is YML. This standard covers the basic description of the application, model parameters, orchestration configuration, and other information.

### Import local DSL file

If you have obtained a template (DSL file) from the community or others, you can choose "Import DSL File" from the studio. After importing, all configuration information of the original application will be loaded directly.

![Import_DSL_file](/Application_Orchestration/images/Import_DSL_file.png)

## Import DSL file from URL

You can also import DSL files via a URL, using the following link format:

```
https://example.com/your_dsl.yml
```

![Import_DSL_via_URL](/Application_Orchestration/images/Import_DSL_via_URL.png)
