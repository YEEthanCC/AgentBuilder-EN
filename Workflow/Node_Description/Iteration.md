# Iteration

## Definition

Execute multiple steps on an array until all results are output.

The iteration step performs the same steps on each item in a list. To use iteration, ensure that the input value is formatted as a list object. The iteration node allows AI workflows to handle more complex processing logic. It is a user-friendly version of the loop node, making some compromises in customization to allow non-technical users to quickly get started.

## Scenarios

### Example 1: Long Article Iteration Generator

![long_story_generator](/Workflow/Node_Description/images/long_story_generator.png)

1. Enter the story title and outline in the Start Node.
2. Use a Generate Subtitles and Outlines Node to use LLM to generate the complete content from user input.
3. Use a Extract Subtitles and Outlines Node to convert the complete content into an array format.
4. Use an Iteration Node to wrap an LLM Node and generate content for each chapter through multiple iterations.
5. Add a Direct Answer Node inside the iteration node to achieve streaming output after each iteration.

### Detailed Configuration Steps

1. Configure the story title (title) and outline (outline) in the **Start Node**. 

![start_node_config](/Workflow/Node_Description/images/start_node_config.png)

2. Use a **Generate Subtitles and Outlines Node** to convert the story title and outline into complete text.

![llm_node_config](/Workflow/Node_Description/images/llm_node_config.png)

3. Use a **Extract Subtitles and Outlines Node** to convert the story text into an array (Array) structure. The parameter to extract is ```sections```, and the parameter type is ```Array[Object]```.

![parameter_extraction](/Workflow/Node_Description/images/parameter_extraction.png)

The effectiveness of parameter extraction is influenced by the model's inference capability and the instructions given. Using a model with stronger inference capabilities and adding examples in the ```instructions``` can improve the parameter extraction results.

4. Use the array-formatted story outline as the input for the iteration node and process it within the iteration node using an **LLM Node**.

![iteration_node_config](/Workflow/Node_Description/images/iteration_node_config.png)

Configure the input variables ```GenerateOverallOutline/output``` and ```Iteration/item``` in the LLM Node.

![iteration_llm_node_config](/Workflow/Node_Description/images/iteration_llm_node_config.png)

Built-in variables for iteration: ```items[object]``` and ```index[number]```.
```items[object]``` represents the input item for each iteration;
```index[number]``` represents the current iteration round;

5. Configure a **Direct Reply Node** inside the iteration node to achieve streaming output after each iteration.

![direct_reply_node](/Workflow/Node_Description/images/direct_reply_node.png)

6. Complete debugging and preview.

![direct_reply_generation](/Workflow/Node_Description/images/direct_reply_generation.png)

### Example 2: Long Article Iteration Generator (Another Arrangement)

![longstory_generation](/Workflow/Node_Description/images/longstory_generation.png)

- Enter the story title and outline in the **Start Node**.
- Use an **LLM Node** to generate subheadings and corresponding content for the article.
- Use a **Code Node** to convert the complete content into an array format.
- Use an **Iteration Node** to wrap an **LLM Node** and generate content for each chapter through multiple iterations.
- Use a **Template Conversion** Node to convert the string array output from the iteration node back to a string.
- Finally, add a **Direct Reply Node** to directly output the converted string.

## What is Array Content
A list is a specific data type where elements are separated by commas and enclosed in ```[``` and ```]```. For example:

### Numeric:
```
[0,1,2,3,4,5]
```
### String:
```
["Monday", "Tuesday", "Wednesday", "Thursday"]
```
### JSON Object:
```
[
    {
        "name": "Alice",
        "age": 30,
        "email": "alice@example.com"
    },
    {
        "name": "Bob",
        "age": 25,
        "email": "bob@example.com"
    },
    {
        "name": "Charlie",
        "age": 35,
        "email": "charlie@example.com"
    }
]
```

## Nodes Supporting Array Return

- Code Node
- Parameter Extraction
- Knowledge Base Retrieval
- Iteration
- Tools
- HTTP Request

## How to Obtain Array-Formatted Content

### Return Using the CODE Node

![parameter_extraction](/Workflow/Node_Description/images/parameter_extraction.png)

## How to Convert an Array to Text

The output variable of the iteration node is in array format and cannot be directly output. You can use a simple step to convert the array back to text.

### Convert Using a Code Node

CODE Example:
```
def main(articleSections: list):
    data = articleSections
    return {
        "result": "/n".join(data)
    }
```

### Convert Using a Template Node

![template_node_config](/Workflow/Node_Description/images/template_node_config.png)

CODE Example:
```
{{ articleSections | join("/n") }}
```
