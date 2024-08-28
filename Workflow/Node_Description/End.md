# End

## 1 Definition

Define the final output content of a workflow. Every workflow needs at least one end node after complete execution to output the final result.

The end node is a termination point in the process; no further nodes can be added after it. In a workflow application, results are only output when the end node is reached. If there are conditional branches in the process, multiple end nodes need to be defined.

The end node must declare one or more output variables, which can reference any upstream node's output variables.

End nodes are not supported within Chatflow.

## 2 Scenarios

In the following long story generation workflow, the variable ```Output``` declared by the end node is the output of the upstream code node. This means the workflow will end after the Code node completes execution and will output the execution result of Code.

![storyWriter_end](/Workflow/Node_Description/images/storyWriter_end.png)

### Single Path Execution Example:

![singlePath_end](/Workflow/Node_Description/images/singlePath_end.png)

### Multi-Path Execution Example:

![multiPath_end](/Workflow/Node_Description/images/multiPath_end.png)