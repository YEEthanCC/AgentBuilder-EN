# Logs and Annotation

Please ensure that your application complies with local regulations when collecting user data. The common practice is to publish a privacy policy and obtain user consent.

The **Logs** feature is designed to observe and annotate the performance of AgentBuilder applications. AgentBuilder records logs for all interactions with the application, whether through the WebApp or API. If you are a Prompt Engineer or LLM operator, it will provide you with a visual experience of LLM application operations.

## Using the Logs Console

You can find the Logs in the left navigation of the application. This page typically displays:

- Interaction records between users and AI within the selected timeframe
- The results of user input and AI output, which for conversational applications are usually a series of message flows
- Ratings from users and operators, as well as improvement annotations from operators

The logs currently do not include interaction records from the Prompt debugging process.

## Improvement Annotations

These annotations will be used for model fine-tuning in future versions of AgentBuilder to improve model accuracy and response style. The current preview version only supports annotations. 

![mark_logs](/Annotation/images/mark_logs.png) 

Clicking on a log entry will open the log details panel on the right side of the interface. In this panel, operators can annotate an interaction:

- Give a thumbs up for well-performing messages
- Give a thumbs down for poorly-performing messages
- Mark improved responses for improvement, which represents the text you expect AI to reply with

Please note that if multiple administrators in the team annotate the same log entry, the last annotation will overwrite the previous ones.