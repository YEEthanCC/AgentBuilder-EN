# Developing with APIs

AgentBuilder offers a "Backend-as-a-Service" API, providing numerous benefits to AI application developers. This approach enables developers to access the powerful capabilities of large language models (LLMs) directly in frontend applications without the complexities of backend architecture and deployment processes.

## Benefits of using AgentBuilder API

- Allow frontend apps to securely access LLM capabilities without backend development
- Design applications visually with real-time updates across all clients
- Well-encapsulated original LLM APIs
- Effortlessly switch between LLM providers and centrally manage API keys
- Operate applications visually, including log analysis, annotation, and user activity observation
- Continuously provide more tools, plugins, and knowledge

## How to use 

Choose an application, and find the API Access in the left-side navigation of the Apps section. On this page, you can view the API documentation provided by AgentBuilder and manage credentials for accessing the API.

API document
You can create multiple access credentials for an application to deliver to different users or developers. This means that API users can use the AI capabilities provided by the application developer, but the underlying Prompt engineering, knowledge, and tool capabilities are encapsulated.

In best practices, API keys should be called through the backend, rather than being directly exposed in plaintext within frontend code or requests. This helps prevent your application from being abused or attacked.

For example, if you're a developer in a consulting company, you can offer AI capabilities based on the company's private database to end-users or developers, without exposing your data and AI logic design. This ensures a secure and sustainable service delivery that meets business objectives.

## Text-generation application

These applications are used to generate high-quality text, such as articles, summaries, translations, etc., by calling the completion-messages API and sending user input to obtain generated text results. The model parameters and prompt templates used for generating text depend on the developer's settings in the AgentBuilder Prompt Arrangement page.

You can find the API documentation and example requests for this application in **Applications -> Access API**.

For example, here is a sample call an API for text generation: 

```
curl -X POST 'https://api-chatbase-chatbase-ensaas.dev003.wise-paas.com/v1/completion-messages' \
--header 'Authorization: Bearer {api_key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "inputs": {"query": "Hello, world!"},
    "response_mode": "streaming",
    "user": "abc-123"
}'
```

## Conversational applications

Suitable for most scenarios, conversational applications engage in continuous dialogue with users in a question-and-answer format. To start a conversation, call the chat-messages API and maintain the session by continuously passing in the returned conversation_id.

You can find the API documentation and example requests for this application in **Applications -> Access API**.

For example, here is a sample call an API for chat-messages: 

```
curl -X POST 'https://api-chatbase-chatbase-ensaas.dev003.wise-paas.com/v1/chat-messages' \
--header 'Authorization: Bearer {api_key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "inputs": {},
    "query": "What are the specs of the iPhone 13 Pro Max?",
    "response_mode": "streaming",
    "conversation_id": "",
    "user": "abc-123",
    "files": [
      {
        "type": "image",
        "transfer_method": "remote_url",
        "url": "https://cloud.AgentBuilder.ai/logo/logo-site.png"
      }
    ]
}'
```