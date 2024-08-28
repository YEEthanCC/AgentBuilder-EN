# Question Classifier

## 1. Definition

By defining classification descriptions, the issue classifier can infer and match user inputs to the corresponding categories and output the classification results.

## 2. Scenarios

Common use cases include **conversation intent classification, product review classification, and bulk email classification**.

The issue classifier can serve as a preliminary step before knowledge base retrieval. It classifies the user's input question, directing it to different downstream knowledge base queries to accurately respond to the user's question.

The following diagram is an example workflow template:

![question_classifier_chatflow](/Workflow/Node_Description/images/question_classifier_chatflow.png)

In this scenario, we set up three classification labels/descriptions:

- Category 1: **Questions related to fire safety**
- Category 2: **Questions related to job usage**
- Category 3: **Other questions**

When users input different questions, the issue classifier will automatically classify them based on the set classification labels/descriptions:

- **"A fire started, what should I do?" —> "Questions related to fire safety"**
- **"What is occupational contraindication?" —> "Questions related to job safety"**
- **"How's the weather today?" —> "Other questions"**

## 3. How to Configure

![configure_classifier](/Workflow/Node_Description/images/configure_classifier.png)

### Configuration Steps:

1. **Select Input Variable**: This refers to the content to be classified, usually the user's question in a customer service Q&A scenario, e.g., ```sys.query```.
2. **Choose Inference Model**: The issue classifier leverages the natural language classification and inference capabilities of large language models. Selecting an appropriate model can enhance classification effectiveness.
3. **Write Classification Labels/Descriptions**: You can manually add multiple classifications by writing keywords or descriptive statements for each category, helping the large language model better understand the classification criteria.
4. **Choose Corresponding Downstream Nodes**: After classification, the issue classification node can direct the flow to different paths based on the relationship between the classification and downstream nodes.

### Advanced Settings:

**Instructions**: In **Advanced Settings - Instructions**, you can add supplementary instructions, such as more detailed classification criteria, to enhance the classifier's capabilities.

**Memory**: When enabled, each input to the issue classifier will include chat history from the conversation to help the LLM understand the context and improve question comprehension in interactive dialogues.

**Memory Window**: When the memory window is closed, the system dynamically filters the amount of chat history passed based on the model's context window; when open, users can precisely control the amount of chat history passed (in terms of numbers).

### Output Variable:

```class_name```

This is the classification name output after classification. You can use the classification result variable in downstream nodes as needed.