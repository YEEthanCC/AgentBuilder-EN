# Maintain Knowledge Base via API

Authentication and invocation methods are consistent with the application Service API. The difference is that a single knowledge base API token can operate on all knowledge bases.

## Advantages of Using Knowledge Base API

- Synchronize your data system with Dify knowledge bases to create powerful workflows.
- Provide knowledge base list, document list, and detail queries to facilitate building your own data management page.
- Support both plain text and file uploads and updates for documents, and support batch addition and modification at the segment level to streamline your synchronization process.
- Reduce the time spent on manual document processing and synchronization, enhancing your visibility into Dify's software and services.

## How to Use

Navigate to the knowledge base page, and you can switch to the **API ACCESS** page from the left navigation. On this page, you can view the dataset API documentation provided by Dify and manage the credentials for accessing the dataset API in **API Keys**. 

![knowledge_api_document](/Knowledge_Base/images/knowledge_api_document.png) 

## API Call Examples

### Create an Empty Dataset 

```
curl --location --request POST 'https://api-chatbase-chatbase-ensaas.dev003.wise-paas.com/v1/datasets' \
--header 'Authorization: Bearer {api_key}' \
--header 'Content-Type: application/json' \
--data-raw '{"name": "name"}'
```

### Dataset List

```
curl --location --request GET 'https://api-chatbase-chatbase-ensaas.dev003.wise-paas.com/v1/datasets?page=1&limit=20' \
--header 'Authorization: Bearer {api_key}'
``` 

### Create Document by Text

```
curl --location --request POST 'https://api-chatbase-chatbase-ensaas.dev003.wise-paas.com/v1/datasets/{dataset_id}/document/create_by_text' \
--header 'Authorization: Bearer {api_key}' \
--header 'Content-Type: application/json' \
--data-raw '{"name": "text","text": "text","indexing_technique": "high_quality","process_rule": {"mode": "automatic"}}'
```

### Create Document by File

```
curl --location --request POST 'https://api-chatbase-chatbase-ensaas.dev003.wise-paas.com/v1/datasets/{dataset_id}/document/create_by_file' \
--header 'Authorization: Bearer {api_key}' \
--form 'data="{"indexing_technique":"high_quality","process_rule":{"rules":{"pre_processing_rules":[{"id":"remove_extra_spaces","enabled":true},{"id":"remove_urls_emails","enabled":true}],"segmentation":{"separator":"###","max_tokens":500}},"mode":"custom"}}";type=text/plain' \
--form 'file=@"/path/to/file"'
```

### Get Document Embedding Status (Progress)

```
curl --location --request GET 'https://api-chatbase-chatbase-ensaas.dev003.wise-paas.com/v1/datasets/{dataset_id}/documents/{batch}/indexing-status' \
--header 'Authorization: Bearer {api_key}'
```

### Delete Document 

```
curl --location --request DELETE 'https://api-chatbase-chatbase-ensaas.dev003.wise-paas.com/v1/datasets/{dataset_id}/documents/{document_id}' \
--header 'Authorization: Bearer {api_key}'
```

### Dataset Document List

```
curl --location --request GET 'https://api-chatbase-chatbase-ensaas.dev003.wise-paas.com/v1/datasets/{dataset_id}/documents' \
--header 'Authorization: Bearer {api_key}'
``` 

### Add Segments

```
curl --location --request POST 'https://api-chatbase-chatbase-ensaas.dev003.wise-paas.com/v1/datasets/{dataset_id}/documents/{document_id}/segments' \
--header 'Authorization: Bearer {api_key}' \
--header 'Content-Type: application/json' \
--data-raw '{"segments": [{"content": "1","answer": "1","keywords": ["a"]}]}'
```

### Delete Document Segment

```
curl --location --request DELETE 'https://api-chatbase-chatbase-ensaas.dev003.wise-paas.com/v1/datasets/{dataset_id}/segments/{segment_id}' \
--header 'Authorization: Bearer {api_key}' \
--header 'Content-Type: application/json'
```

## Error Messages

- ```document_indexing```: Document indexing failed
- ```provider_not_initialize```: Embedding model not configured
- ```not_found```: Document not found
- ```dataset_name_duplicate```: Dataset name duplicate
- ```provider_quota_exceeded```: Model quota exceeded
- ```dataset_not_initialized```: Dataset not initialized
- ```unsupported_file_type```: Unsupported file type
    - Currently supported: txt, markdown, md, pdf, html, htm, xlsx, docx, csv
- ```too_many_files: Too many files```, currently only single file uploads are supported
- ```file_too_large```: File too large, supports files under 15MB