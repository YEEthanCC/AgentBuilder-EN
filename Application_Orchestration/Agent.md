# Agent

## Definition

An Agent Assistant can leverage the reasoning abilities of large language models (LLMs). It independently sets goals, simplifies complex tasks, operates tools, and refines processes to complete tasks autonomously.

## Usage Instructions

To facilitate quick learning and use, application templates for the Agent Assistant are available in the 'Explore' section. You can integrate these templates into your workspace. The new AgentBuilder 'Studio' also allows the creation of a custom Agent Assistant to suit individual requirements. This assistant can assist in analyzing financial reports, composing reports, designing logos, and organizing travel plans.

![explore_agent_template](/Application_Orchestration/images/explore_agent_template.png)

The task completion ability of the Agent Assistant depends on the inference capabilities of the model selected. We recommend using a more powerful model series like GPT-4 when employing Agent Assistant to achieve more stable task completion results.

![select_model_for_agent](/Application_Orchestration/images/select_model_for_agent.png)

You can write prompts for the Agent Assistant in 'Instructions'. To achieve optimal results, you can clearly define its task objectives, workflow, resources, and limitations in the instructions.

![Agent_prompt](/Application_Orchestration/images/Agent_prompt.png)

## Adding Tools for the Agent Assistant
In the "Context" section, you can incorporate knowledge base tools that the Agent Assistant can utilize for information retrieval. This will assist in providing it with external background knowledge.

In the "Tools" section, you are able to add tools that are required for use. These tools can enhance the capabilities of LLMs, such as internet searches, scientific computations, or image creation, thereby enriching the LLM's ability to interact with the real world. AgentBuilder offers two types of tools: **built-in tools and custom tools**.

You have the option to directly use built-in tools in AgentBuilder, or you can easily import custom API tools (currently supporting OpenAPI/Swagger and OpenAI Plugin standards).

![Add_agent_tools](/Application_Orchestration/images/Add_agent_tools.png)

The tool allows you to create more powerful AI applications on AgentBuilder. For example, you can orchestrate suitable tools for Agent Assistant, enabling it to complete complex tasks through reasoning, step decomposition, and tool invocation. Additionally, the tool facilitates the integration of your application with other systems or services, allowing interaction with the external environment, such as code execution and access to exclusive information sources.

## Agent Settings

On AgentBuilder, two inference modes are provided for Agent Assistant: Function Calling and ReAct. Models like GPT-3.5 and GPT-4 that support Function Calling have demonstrated better and more stable performance. For model series that do not support Function Calling, we have implemented the ReAct inference framework to achieve similar effects.

In the Agent settings, you can moAgentBuilder the iteration limit of the Agent.

![Agent_settings](/Application_Orchestration/images/Agent_settings.png)

## Configuring the Conversation Opener

You can set up a conversation opener and initial questions for your Agent Assistant. The configured conversation opener will be displayed at the beginning of each user's first interaction, showcasing the types of tasks the Agent can perform, along with examples of questions that can be asked.

![Agent_conversation_operner](/Application_Orchestration/images/Agent_conversation_operner.png)

## Debugging and Preview

After orchestrating your Agent Assistant, you have the option to debug and preview it before publishing it as an application. This allows you to assess the effectiveness of the agent in completing tasks.

![Preview_agent](/Application_Orchestration/images/Preview_agent.png)

## Application Publish

![Publish_agent](/Application_Orchestration/images/Publish_agent.png)
