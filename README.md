# file-to-markdown api

welcome to the **file-to-markdown api**, a streamlined solution that lets you convert various document formats directly into markdown with extracted tables and concise text. this api is designed to be efficient, free to use, and does not rely on any large language models—just pure code.

## overview

the file-to-markdown api allows you to post files (`.docx`, `.pdf`, `.xls`, `.xlsx`, `.xlsb`, and `.xlsm`) and receive the content back markdown. the API is primarily for retrieval augmented generation (RAG) app developers, as converting to markdown may be beneficial especially if you need LLM to parse through complex documents and spreadsheets.


![GSzXXpWW4AA1rCP](https://github.com/user-attachments/assets/210894f5-9f37-42e7-a280-de2e762a2ab2)


## features

- free api for LLM devs.
- instant transformation of word, pdf, and excel into markdown.
- no LLM used. no API keys needed.
- custom parsing captures tables and represents them accurately in markdown.

**api request**: use the following python example to make a post request to the api:

```python
import requests

file_path = 'path/to/your/document.pdf' <---------------your file
api_endpoint = 'https://devgs-markdown-parser/upload/'

with open(file_path, 'rb') as file:
    response = requests.post(
        api_endpoint,
        files={'file': file}
    )

# output the JSON response (markdown content)
response_data = response.json()
```

response: the API responds with a JSON object containing the Markdown content. simply parse this response to retrieve and use your formatted text.

```python
# clean print
if response_data.get("status") == "success":
    markdown_text = response_data.get("markdown", "")
    print(markdown_text)
else:
    error_message = response_data.get("message", "Unknown error")
    print(f"Error: {error_message}")
```

## use for

- primarily created for LLM devs who build RAG apps.
- any other where you need instant markdown.
  
## updates

i will be adding more file formats and improving this api going forward to better support developers in the llm community.
