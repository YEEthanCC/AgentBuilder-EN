# Tools

## Tool Definition

Tools can extend the capabilities of LLMs (Language Learning Models), such as performing web searches, scientific calculations, or 
generating images, thereby enhancing the LLM's ability to connect with the external world. AgentBuilder provides two types of tools: **First-party Tools** and **Custom Tools**.

You can directly use the first-party built-in tools provided by the AgentBuilder ecosystem, or easily import custom API tools (currently supporting OpenAPI / Swagger and OpenAI Plugin specifications).

### Functions of Tools:

1. Tools allow users to create more powerful AI applications on AgentBuilder. For example, you can arrange suitable tools for an intelligent assistant application (Agent) that can complete complex tasks through task reasoning, step-by-step breakdown, and tool invocation.
2. They facilitate connecting your application with other systems or services and interacting with the external environment, such as code execution or access to proprietary information sources.

## How to Configure First-party Tools

![first_party_tool_list](/Tools/images/first_party_tool_list.png)

AgentBuilder currently supports:

|**Tool**|**Description**|
|:-------|:--------------|
|Google Search|Tool for performing Google SERP searches and extracting snippets and web pages. The input should be a search query.|
|Wikipedia|Tool for performing Wikipedia searches and extracting snippets and web pages.|
|DALL-E Drawing|Tool for generating high-quality images through natural language input.|
|Web Scraping|Tool for scraping web data.|
|WolframAlpha|A powerful computational knowledge engine that provides standardized answers based on questions and has strong mathematical computation capabilities.|
|Chart Generation|Tool for generating visual charts, allowing you to create bar charts, line charts, pie charts, and other types of charts.|
|Current Time|Tool for querying the current time.|
|Yahoo Finance|Tool for obtaining and organizing the latest financial information, such as news and stock quotes.|
|Stable Diffusion|A tool for generating images that can be deployed locally using stable-diffusion-webui.|
|Vectorizer|Tool for quickly and easily converting PNG and JPG images to SVG vector graphics.|
|YouTube|Tool for retrieving statistics of YouTube channel videos.|

### First-party Tool Authorization

If you need to use the first-party built-in tools provided by the AgentBuilder ecosystem, you need to configure the corresponding credentials before using them.

![first_party_tool_configure](/Tools/images/first_party_tool_configure.png)

Once the credentials are successfully verified, the tool will display an "Authorized" status. After configuring the credentials, all members in the workspace can use this tool when arranging applications.

## How to Create Custom Tools
You can import custom API tools in the "Tools - Custom Tools" section, currently supporting OpenAPI / Swagger and ChatGPT Plugin specifications. You can directly paste the OpenAPI schema content or import it from a URL. For the OpenAPI / Swagger specification, you can refer to the [official documentation](https://swagger.io/specification/).

Currently, tools support two authentication methods: No Authentication and API Key. 

![create_custome_tools](/Tools/images/create_custome_tools.png) 

After importing the schema content, the system will automatically parse the parameters in the file, and you can preview the specific parameters, methods, and paths of the tool. You can also test the tool parameters here.

![custom_tool_test](/Tools/images/custom_tool_test.png) 

Once the custom tool is created, all members in the workspace can use this tool when arranging applications in the "Studio." 

![custom_tool_added](/Tools/images/custom_tool_added.png) 

## How to Use Tools in Applications

Currently, you can use the configured tools when creating **intelligent assistant applications** in the "Studio." 

![add_tools_agent](/Tools/images/add_tools_agent.png) 

For example, after adding tools in a financial analysis application, the intelligent assistant will autonomously invoke tools when needed to query financial report data, analyze the data, and complete the conversation with the user.

![financial_analysis_tool](/Tools/images/financial_analysis_tool.png) 