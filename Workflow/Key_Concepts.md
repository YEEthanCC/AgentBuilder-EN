# Key Concepts

## Nodes

**Nodes are the key components of a workflow**. By connecting nodes with different functionalities, you can execute a series of operations within the workflow.

## Variables

**Variables are used to link the input and output of nodes within a workflow**, enabling complex processing logic throughout the process. Fore more details, please take refer to Variables.

## Chatflow and Workflow

### Application Scenarios

- **Chatflow**: Designed for conversational scenarios, including customer service, semantic search, and other conversational applications that require multi-step logic in response construction.
- **Workflow**: Geared towards automation and batch processing scenarios, suitable for high-quality translation, data analysis, content generation, email automation, and more.

### Usage Entry Points

![chatflow_entry](/Workflow/images/chatflow_entry.png)

![workflow_entry](/Workflow/images/workflow_entry.png)

### Differences in Available Nodes

1. The End node is an ending node for Workflow and can only be selected at the end of the process.
2. The Answer node is specific to Chatflow, used for streaming text output, and can output at intermediate steps in the process.
3. Chatflow has built-in chat memory (Memory) for storing and passing multi-turn conversation history, which can be enabled in nodes like LLM and question classifiers. Workflow does not have Memory-related configurations and cannot enable them.
4. Built-in variables for Chatflow's start node include: ```sys.query```, ```sys.files```, ```sys.conversation_id```, ```sys.user_id```. Built-in variables for Workflow's start node include: ```sys.files```, ```sys_id```.

