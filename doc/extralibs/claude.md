## Anthropic Claude

The Anthropic Python library provides convenient access to the 
Anthropic Claude API from applications written in the Python language. 

To use the Anthropic Claude API, you first need to have your Anthropic Claude API key.

<div class="notebox notebox-danger">
    <p class="notebox-title">
        Warning
    </p>
    <p>
        When including private API keys in your code, make sure you <b>DO NOT</b> make your project <b>"Open Source"</b> when you share it.
    </p>
</div>

### Examples

```python
from anthropic import Anthropic

api_key = input("🤖 What's your Anthropic API Key?\n")
client = Anthropic(api_key=api_key)

question = input("🤖 What's your question?\n")
print("🤖 Please wait a second ...")

message = client.messages.create(
    max_tokens=1024,
    messages=[
        {
            "role": "user",
            "content": question,
        }
    ],
    model="claude-sonnet-4-6",
)

print("🤖", message.content[0].text)
```

### Reference

* [Claude Python SDK API Reference](https://platform.claude.com/docs/en/api/sdks/python)
* [Github: anthropic-sdk-python source code](https://github.com/anthropics/anthropic-sdk-python)