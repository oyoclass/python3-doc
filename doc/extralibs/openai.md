## OpenAI

The OpenAI Python library provides convenient access to the OpenAI API from applications written in the Python language. It includes a pre-defined set of classes for API resources that initialize themselves dynamically from API responses which makes it compatible with a wide range of versions of the OpenAI API <sup>\[1\]</sup>.

To use the openAI's API, you first need to have your openAI's API key. To do so, you could register your account in [https://platform.openai.com/](https://platform.openai.com/), then go to your [account API-key settings](https://platform.openai.com/account/api-keys), click _"+ Create new secret key"_ to generate an API key, then you copy the key and use it in the sample code below. 

For a step-by-step tutorial on how to obtain the API key, please <a href="https://docs.oyoclass.com/cloudservices/ai/openai/" target="_blank">click here</a>.

<div class="notebox notebox-danger">
    <p class="notebox-title">
        Warning
    </p>
    <p>
        When including private API keys in your code, make sure you <b>DO NOT</b> make your project <b>"Open Source"</b> when you share it.
    </p>
</div>

### Examples

#### Built AI to answer question

```python
import openai

api_key = input("🤖 What's your openAI's API Key?\n")
client = openai.OpenAI(api_key=api_key)

question = input("🤖 What's your question?\n")
print("🤖 Please wait a second ...")

completion = client.chat.completions.create(
  model="gpt-3.5-turbo",
  messages=[
        {"role": "system", "content": "You are ChatGPT"},
        {"role": "user", "content": question},
    ]
)

answer = completion.choices[0].message.content
print("🤖", answer)
```

For more information on how to use the openAI library, see the [official openAI documentation](https://platform.openai.com/docs/introduction) <sup>\[2\]</sup>.

### Reference

1. [https://pypi.org/project/openai/](https://pypi.org/project/openai/)
1. [openAI's official documentation](https://platform.openai.com/docs/introduction)
