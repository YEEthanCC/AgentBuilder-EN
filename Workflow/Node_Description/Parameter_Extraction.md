# Parameter Extraction

## 1 Definition

Utilize LLM to infer and extract structured parameters from natural language for subsequent tool invocation or HTTP requests.

AgentBuilder workflows provide a rich selection of tools, most of which require structured parameters as input. The parameter extractor can convert user natural language into parameters recognizable by these tools, facilitating tool invocation.

Some nodes within the workflow require specific data formats as inputs, such as the iteration node, which requires an array format. The parameter extractor can conveniently achieve structured parameter conversion.

## 2 Scenarios

1. **Extracting key parameters required by tools from natural language**, such as building a simple conversational Arxiv paper retrieval application.

In this example: The Arxiv paper retrieval tool requires **paper author** or **paper ID** as input parameters. The parameter extractor extracts the paper ID **2405.10739** from the query "What is the content of this paper: 2405.10739" and uses it as the tool parameter for precise querying.

![arxiv_tool](/Workflow//Node_Description//images/arxiv_tool.png)

2. **Converting text to structured data**, such as in the long story iteration generation application, where it serves as a pre-step for the iteration node, converting chapter content in text format to an array format, facilitating multi-round generation processing by the iteration node.

![parameter_extractor](/Workflow//Node_Description//images/parameter_extractor.png)

3. **Extracting structured data and using the HTTP Request**, which can request any accessible URL, suitable for obtaining external retrieval results, webhooks, generating images, and other scenarios. 

## 3 How to Configure

### Configuration Steps

1. Select the input variable, usually the variable input for parameter extraction.
2. Choose the model, as the parameter extractor relies on the LLM's inference and structured generation capabilities.
3. Define the parameters to extract, which can be manually added or **quickly imported from existing tools**.
4. Write instructions, where providing examples can help the LLM improve the effectiveness and stability of extracting complex parameters.

### Advanced Settings

### Inference Mode

Some models support two inference modes, achieving parameter extraction through function/tool calls or pure prompt methods, with differences in instruction compliance. For instance, some models may perform better in prompt inference if function calling is less effective.

- Function Call/Tool Call
- Prompt

### Memory

When memory is enabled, each input to the question classifier will include the chat history in the conversation to help the LLM understand the context and improve question comprehension during interactive dialogues.

### Output Variables

- Extracted defined variables
- Node built-in variables

```__is_success Number``` Extraction success status, with a value of 1 for success and 0 for failure.
```__reason String``` Extraction error reason