
## Google Gemini

The google-genai Python library provides convenient access to the 
Google Gemini API from applications written in the Python language. 

To use the Google Gemini API, you first need to have your Google Gemini API key.

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
from google import genai

api_key = input("🤖 What's your Gemini API Key?\n")
client = genai.Client(api_key=api_key)

question = input("🤖 What's your question?\n")
print("🤖 Please wait a second ...")

response = client.models.generate_content(
    model='gemini-3-flash-preview',
    contents=question,
)
print("🤖", response.text)
```

### Reference

* [Google Gemini API Reference](https://ai.google.dev/gemini-api/docs#python) 
* [Gemini Models](https://ai.google.dev/gemini-api/docs/models)