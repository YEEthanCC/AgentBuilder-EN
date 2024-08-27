# Application Orchestration

In AgentBuilder, an "application" refers to a practical scenario application built on large language models like GPT. By creating an application, you can apply intelligent AI technology to specific needs. It encompasses both the engineering paradigm for developing AI applications and the specific deliverables.

In short, an application provides developers with:

- A user-friendly API that can be directly called by backend or frontend applications, authenticated via Token
- A ready-to-use, aesthetically pleasing, and hosted WebApp, which you can further develop using the WebApp template
- An easy-to-use interface that includes prompt engineering, context management, log analysis, and annotation

You can choose **any one** or **all** of these to support your AI application development.

## Application Types

AgentBuilder offers four types of applications:

- **Chat Assistant**: A conversational assistant built on LLM
- **Text Generation**: An assistant for text generation tasks such as writing stories, text classification, translation, etc.
- **Agent**: A conversational intelligent assistant capable of task decomposition, reasoning, and tool invocation
- **Workflow**: Defines more flexible LLM workflows based on process orchestration

The differences between Text Generation and Chat Assistant are shown in the table below:

|	|**Text Generation**|**Chat Assistant**|
|:--|:------------------|:-----------------|
|WebApp Interface|Form + Results|Chat-based|
|WebAPI Endpoint|```completion-messages```|```chat-messages```|
|Interaction Mode|One question, one answer|Multi-turn conversation|
|Streaming Results|Supported|Supported|
|Context Preservation|Per session|Continuous|
|User Input Form|Supported|Supported|
|Datasets and Plugins|Supported|Supported|
|AI Opening Remarks|Not supported|Supported|
|Example Scenarios|Translation, judgment, indexing|Chatting|