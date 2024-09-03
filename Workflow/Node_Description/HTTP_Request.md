# HTTP Request

## 1. Definition

Allows sending server requests via the HTTP protocol, suitable for scenarios such as retrieving external data, webhooks, generating images, and downloading files. It enables you to send customized HTTP requests to specified web addresses, achieving interconnectivity with various external services.

This node supports common HTTP request methods:

- **GET**: Used to request the server to send a specific resource.
- **POST**: Used to submit data to the server, typically for submitting forms or uploading files.
- **HEAD**: Similar to GET requests, but the server only returns the response headers without the resource body.
- **PATCH**: Used to apply partial modifications to a resource.
- **PUT**: Used to upload resources to the server, typically for updating an existing resource or creating a new one.
- **DELETE**: Used to request the server to delete a specified resource.

You can configure various aspects of the HTTP request, including URL, request headers, query parameters, request body content, and authentication information.

![http_request_config](/Workflow/Node_Description/images/http_request_config.png)

## 2. Scenarios

One practical feature of this node is the ability to dynamically insert variables into different parts of the request based on the scenario. For example, when handling customer feedback requests, you can embed variables such as username or customer ID, feedback content, etc., into the request to customize automated reply messages or fetch specific customer information and send related resources to a designated server. 

![customer_feedback_classification](/Workflow/Node_Description/images/customer_feedback_classification.png)

The return values of an HTTP request include the response body, status code, response headers, and files. Notably, if the response contains a file (currently only image types are supported), this node can automatically save the file for use in subsequent steps of the workflow. This design not only improves processing efficiency but also makes handling responses with files straightforward and direct.