# Moderation Tool

In our interactions with AI applications, we often have stringent requirements in terms of content security, user experience, and legal regulations. At this point, we need the "Sensitive Word Review" feature to create a better interactive environment for end-users. On the orchestration page, click "Add Feature" and locate the "Content Review" toolbox at the bottom:

![moderation_tool](/Application_Orchestration/Application_Toolkits/images/moderation_tool.png)

## Call the OpenAI Moderation API

OpenAI, along with most companies providing LLMs, includes content moderation features in their models to ensure that outputs do not contain controversial content, such as violence, sexual content, and illegal activities. Additionally, OpenAI has made this content moderation capability available, which you can refer to OpenAI's Moderation.

Now you can also directly call the OpenAI Moderation API on AgentBuilder; you can review either input or output content simply by entering the corresponding "preset reply."

![openai_moderation](/Application_Orchestration/Application_Toolkits/images/openai_moderation.png)

## Keywords

Developers can customize the sensitive words they need to review, such as using "kill" as a keyword to perform an audit action when users input. The preset reply content should be "The content is violating usage policies." It can be anticipated that when a user inputs a text chuck containing "kill" at the terminal, it will trigger the sensitive word review tool and return the preset reply content.

![keyword_moderation](/Application_Orchestration/Application_Toolkits/images/keyword_moderation.png)

## Moderation Extension

Different enterprises often have their own mechanisms for sensitive word moderation. When developing their own AI applications, such as an internal knowledge base ChatBot, enterprises need to moderate the query content input by employees for sensitive words. For this purpose, developers can write an API extension based on their enterprise's internal sensitive word moderation mechanisms, which can then be called on AgentBuilder to achieve a high degree of customization and privacy protection for sensitive word review.

![moderation_extension](/Application_Orchestration/Application_Toolkits/images/moderation_extension.png)