# file-to-markdown api

welcome to the **file-to-markdown api**, a streamlined solution that lets you convert various document formats directly into markdown with extracted tables and concise text. this api is designed to be efficient, free to use, and does not rely on any large language models—just pure code.

## overview

the file-to-markdown api allows users to post files such as `.docx`, `.pdf`, `.xls`, `.xlsx`, `.xlsb`, and `.xlsm` and receive the content back in a structured json format. this json includes markdown-formatted text along with extracted tables, enabling easy integration into your applications, blogs, or documentation processes.

## features

- free api for LLM devs.
- instant transformation of word, pdf, and excel into markdown.
- custom parsing captures tables and represents them accurately in markdown.

**api request**: use the following python example to make a post request to the api:

```import requests

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

```
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
- 
## updates

i will be adding more file formats and improving this api going forward to better support developers in the llm community.

## license

the file-to-markdown api is open-source, released under the mit license. feel free to use and modify as needed.
