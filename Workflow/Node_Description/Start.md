# Start

## Definition
Define the initial parameters for starting a workflow.

You can customize the input variables for initiating the workflow in the start node. Every workflow requires a start node.

![workflow_start](/Workflow/Node_Description/images/workflow_start.png)

The start node supports defining input variables of four types:

- Text
- Paragraph
- Dropdown Options
- Number
- File (coming soon)

![start_input](/Workflow/Node_Description/images/start_input.png)

Once configured, the workflow will prompt for the values of the variables defined in the start node during execution.

![start_execution](/Workflow/Node_Description/images/start_execution.png)

Tip: In Chatflow, the start node provides built-in system variables: ```sys.query``` and ```sys.files```.

```sys.query``` is used for user input questions in conversational applications.

```sys.files``` is used for file uploads in conversations, such as uploading an image, which needs to be used in conjunction with an image understanding model.