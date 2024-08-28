# Variables

**Workflow** and **Chatflow** Application are composed of independent nodes. Most nodes have input and output items, but the input and output information for each node is not consistent and dynamic.

**How to use a fixed symbol to refer dynamically changing content?** Variables, as dynamic data containers, can store and transmit unfixed content, being referenced mutually within different nodes, providing flexible information mobility between nodes.

## System Variables
System variables refer to pre-set system-level parameters within Chatflow / Workflow App that can be globally read by other nodes. All system-level variables begin with ```sys```.

Read-only variables marked with "*" symbol.

### Workflow

Workflow type application provides the system variables below:


|**Variables name**|**Data Type**|**Description**|**Remark**|
|:-----------------|:------------|:--------------|:---------|
|```sys.files```|Array[File]|File Parameter: Stores images uploaded by users|The image upload function needs to be enabled in the'Features' section in the upper right corner of the application orchestration page|
|```*sys.user_id```|String|User ID: A unique identifier automatically assigned by the system to each user when they use a workflow application. It is used to distinguish different users|  |

![workflow_system_variable](/Workflow/images/workflow_system_variable.png)

### Chatflow

Chatflow type application provides the following system variables:

|**Variables name**|**Data Type**|**Description**|**Remark**|
|:-----------------|:------------|:--------------|:---------|
|```sys.query```|String|Content entered by the user in the chatting box.|   |
|```sys.files```|Array[File]|File Parameter: Stores images uploaded by users|The image upload function needs to be enabled in the 'Features' section in the upper right corner of the application orchestration page|
|```*sys.dialogue_count```|Number|The number of conversations turns during the user's interaction with a Chatflow application. The count automatically increases by one after each chat round and can be combined with if-else nodes to create rich branching logic. For example, at the Xth conversation turn, LLM will review the conversation history and automatically provide an analysis.| |
|```*sys.conversation_id```|String|A unique ID for the chatting box interaction session, grouping all related messages into the same conversation, ensuring that the LLM continues the chatting on the same topic and context.| |
|```*sys.user_id```|String|A unique ID is assigned for each application user to distinguish different conversation users.|  |

![chatflow_system_variable](/Workflow/images/chatflow_system_variable.png)

## Environment Variables

**Environment variables are used to protect sensitive information involved in workflows**, such as API keys and database passwords used when running workflows. They are stored in the workflow rather than in the code, allowing them to be shared across different environments.

![add_environment_variable](/Workflow/images/add_environment_variable.png)

Supports the following 3 data types:

- String
- Number
- Secret

Environmental variables have the following characteristics:

- Environment variables can be globally referenced within most nodes;
- Environment variable names cannot be duplicated;
- Output variables of nodes are generally read-only and cannot be written to.

## Notice

- To avoid variable name duplication, node naming must not be repeated
- The output variables of nodes are generally fixed variables and cannot be edited
