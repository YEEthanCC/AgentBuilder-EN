# Integrate Langfuse

## 1. What is Langfuse

Langfuse is an open-source LLM engineering platform that helps teams collaborate on debugging, analyzing, and iterating their applications.

Introduction to Langfuse: [https://langfuse.com/](https://langfuse.com/)

## 2. How to Configure Langfuse

1. Register and log in to Langfuse on the [official website](https://langfuse.com/)
2. Create a project in Langfuse. After logging in, click **New** on the homepage to create your own project. The **project** will be used to associate with **applications** in AgentBuilder for data monitoring.

![create_langfuse_project](/Monitoring/Integrate_External_Ops_Tools/images/create_langfuse_project.png) 

Edit a name for the project. 

![edit_langfuse_project_name](/Monitoring/Integrate_External_Ops_Tools/images/edit_langfuse_project_name.png) 

3. Create project API credentials. In the left sidebar of the project, click **Settings** to open the settings. 

![langfuse_project_settings](/Monitoring/Integrate_External_Ops_Tools/images/langfuse_project_settings.png) 

In Settings, click **Create API Keys** to create project API credentials. 

![create_api_keys](/Monitoring/Integrate_External_Ops_Tools/images/create_api_keys.png) 

Copy and save the **Secret Key**, **Public Key**, and **Host**. 

![langfuse_api_keys_config](/Monitoring/Integrate_External_Ops_Tools/images/langfuse_api_keys_config.png) 

4. Configure Langfuse in AgentBuilder. Open the application you need to monitor, open **Monitoring** in the side menu, and select **Tracing app performance** on the page. 

![config_tracing](/Monitoring/Integrate_External_Ops_Tools/images/config_tracing.png) 

After clicking configure, paste the **Secret Key, Public Key, Host** created in Langfuse into the configuration and save. 

![config_langfuse](/Monitoring/Integrate_External_Ops_Tools/images/config_langfuse.png) 

Once successfully saved, you can view the status on the current page. If it shows as started, it is being monitored. 

![langfuse_config_status](/Monitoring/Integrate_External_Ops_Tools/images/langfuse_config_status.png) 

## 3. Viewing Monitoring Data in Langfuse

After configuration, debugging or production data of the application in AgentBuilder can be viewed in Langfuse. 

![debug_app_on_agentBuilder](/Monitoring/Integrate_External_Ops_Tools/images/debug_app_on_agentBuilder.png) 

![app_trace_in_langfuse](/Monitoring/Integrate_External_Ops_Tools/images/app_trace_in_langfuse.png) 

## 4 List of monitoring data

### Trace the information of Workflow and Chatflow

### Tracing workflow and chatflow

|**Workflow**|**LangFuse Trace**| 
|:-----------|:-----------------|
|workflow_app_log_id/workflow_run_id|id|
|user_session_id|user_id|
|workflow_{id}|name|
|start_time|start_time|
|end_time|end_time|
|inputs|input|
|outputs|output|
|Model token consumption|usage|
|metadata|metadata|
|error|level|
|error|status_message|
|[workflow]|tags|
|["message", conversation_mode]|session_id|
|conversion_id|parent_observation_id|

### Workflow Trace Info

- workflow_id - Unique ID of Workflow
- conversation_id - Conversation ID
- workflow_run_id - Workflow ID of this runtime
- tenant_id - Tenant ID
- elapsed_time - Elapsed time at this runtime
- status - Runtime status
- version - Workflow version
- total_tokens - Total token used at this runtime
- file_list - List of files processed
- triggered_from - Source that triggered this runtime
- workflow_run_inputs - Input of this workflow
- workflow_run_outputs - Output of this workflow
- error - Error Message
- query - Queries used at runtime
- workflow_app_log_id - Workflow Application Log ID
- message_id - Relevant Message ID
- start_time - Start time of this runtime
- end_time - End time of this runtime
- workflow node executions - Workflow node runtime information
- Metadata
    - workflow_id - Unique ID of Workflow
    - conversation_id - Conversation ID
    - workflow_run_id - Workflow ID of this runtime
    - tenant_id - Tenant ID
    - elapsed_time - Elapsed time at this runtime
    - status - Operational state
    - version - Workflow version
    - total_tokens - Total token used at this runtime
    - file_list - List of files processed
    - triggered_from - Source that triggered this runtime

### Message Trace Info

### For trace llm conversation
|**Message**|**LangFuse Generation/Trace**|
|:----------|:----------------------------|
|message_id|id|
|user_session_id|user_id|
|message_{id}|name|
|start_time|start_time|
|end_time|end_time|
|inputs|input|
|outputs|output|
|Model token consumption|usage|
|metadata|metadata|
|error|level|
|error|status_message|
|["message", conversation_mode]|tags|
|conversation_id|session_id|
|conversion_id|parent_observation_id| 

### Message Trace Info

- message_id - Message ID
- message_data - Message data
- user_session_id - Session ID for user
- conversation_model - Conversation model
- message_tokens - Message tokens
- answer_tokens - Answer Tokens
- total_tokens - Total Tokens from Message and Answer
- error - Error Message
- inputs - Input data
- outputs - Output data
- file_list - List of files processed
- start_time - Start time
- end_time - End time
- message_file_data - Message of relevant file data
- conversation_mode - Conversation mode
- Metadata
    - conversation_id - Conversation ID
    - ls_provider - Model provider
    - ls_model_name - Model ID
    - status - Message status
    - from_end_user_id - Sending user's ID
    - from_account_id - Sending account's ID
    - agent_based - Whether agent based
    - workflow_run_id - Workflow ID of this runtime
    - from_source - Message source
    - message_id - Message ID

### Moderation Trace Information

### Used to track conversation moderation

|**Moderation**|**LangFuse Generation/Trace**|
|:-------------|:----------------------------|
|user_id|user_id|
|moderation|name|
|start_time|start_time|
|end_time|end_time|
|inputs|input|
|outputs|output|
|metadata|metadata|
|[moderation]|tags|
|message_id|parent_observation_id| 

### Message Trace Info

- message_id - Message ID
- user_id - user ID
- workflow_app_log_id workflow_app_log_id
- inputs - Input data for review
- message_data - Message Data
- flagged - Whether it is flagged for attention
- action - Specific actions to implement
- preset_response - Preset response
- start_time - Start time of review
- end_time - End time of review
- Metadata
    - message_id - Message ID
    - action - Specific actions to implement
    - preset_response - Preset response

### Suggested Question Trace Information

### Used to track suggested questions

|**Suggested Question**|**LangFuse Generation/Trace**|
|:---------------------|:----------------------------|
|user_id|user_id|
|suggested_question|name|
|start_time|start_time|
|end_time|end_time|
|inputs|input|
|outputs|output|
|metadata|metadata|
|[suggested_question]|tags|
|message_id|parent_observation_id|

### Message Trace Info

- message_id - Message ID
- message_data - Message data
- inputs - Input data
- outputs - Output data
- start_time - Start time
- end_time - End time
- total_tokens - Total tokens
- status - Message Status
- error - Error Message
- from_account_id - Sending account ID
- agent_based - Whether agent based
- from_source - Message source
- model_provider - Model provider
- model_id - Model ID
- suggested_question - Suggested question
- level - Status level
- status_message - Message status
- Metadata
    - message_id - Message ID
    - ls_provider - Model Provider
    - ls_model_name - Model ID
    - status - Message status
    - from_end_user_id - Sending user's ID
    - from_account_id - Sending Account ID
    - workflow_run_id - Workflow ID of this runtime
    - from_source - Message source

### Dataset Retrieval Trace Information

### Used to track knowledge base retrieval
|**Dataset Retrieval**|**LangFuse Generation/Trace**|
|user_id|user_id|
|dataset_retrieval|name|
|start_time|start_time|
|end_time|end_time|
|inputs|input|
|outputs|output|
|metadata|metadata|
|[dataset_retrieval]|tags|
|message_id|parent_observation_id|

### Dataset Retrieval Trace Info

- message_id - Message ID
- inputs - Input Message
- documents - Document data
- start_time - Start time
- end_time - End time
- message_data - Message data
- Metadata
    - message_id - Message ID
    - ls_provider - Model Provider
    - ls_model_name - Model ID
    - status - Model status
    - from_end_user_id - Sending user's ID
    - from_account_id - Sending account's ID
    - agent_based - Whether agent based
    - workflow_run_id - Workflow ID of this runtime
    - from_source - Message Source

### Tool Trace Information

### Used to track tool invocation

|**Tool**|**LangFuse Generation/Trace**|
|:-------|:----------------------------|
|user_id|user_id|
|tool_name|name|
|start_time|start_time|
|end_time|end_time|
|inputs|input|
|outputs|output|
|metadata|metadata|
|["tool", tool_name]|tags|
|message_id|parent_observation_id|

### Tool Trace Info

- message_id - Message ID
- tool_name - Tool Name
- start_time - Start time
- end_time - End time
- tool_inputs - Tool inputs
- tool_outputs - Tool outputs
- message_data - Message data
- error - Error Message，if exist
- inputs - Input of Message
- outputs - Output of Message
- tool_config - Tool config
- time_cost - Time cost
- tool_parameters - Tool Parameters
- file_url - URL of relevant files
- Metadata
    - message_id - Message ID
    - tool_name - Tool Name
    - tool_inputs - Tool inputs
    - tool_outputs - Tool outputs
    - tool_config - Tool config
    - time_cost - Time. cost
    - error - Error Message
    - tool_parameters - Tool parameters
    - message_file_id - Message file ID
    - created_by_role - Created by role
    - created_user_id - Created user ID

### Generate Name Trace

### Used to track conversation title generation

|**Generate Name**|**LangFuse Generation/Trace**|
|;----------------|:----------------------------|
|user_id|user_id|
|generate_name|name|
|start_time|start_time|
|end_time|end_time|
|inputs|input|
|outputs|output|
|metadata|metadata|
|[generate_name]|tags|

### Generate Name Trace Info

- conversation_id - Conversation ID
- inputs - Input data
- outputs - Generated session name
- start_time - Start time
- end_time - End time
- tenant_id - Tenant ID
- Metadata
    - conversation_id - Conversation ID
    - tenant_id - Tenant ID