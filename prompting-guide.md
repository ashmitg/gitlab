---
description: >-
  - Prompt Engineering is an essential part of making high-quality models. All
  you gotta do is say, and the model will do!
---

# Prompting Guide

{% embed url="https://colab.research.google.com/drive/1eMRidYrys3b1mPrhUOJnfAB3Z7tcCNn0?usp=sharing#scrollTo=Z4an7STNqmmx" %}
Prompt Guide overview
{% endembed %}

## Import the library

Now, you will have to install the chaiverse package and import the dependencies

{% tabs %}
{% tab title="Python" %}
```
import chaiverse as chai
from chaiverse.formatters import PromptFormatter
```
{% endtab %}
{% endtabs %}

## How it works

{% content-ref url="how-everything-works/prompt-guiding-explained.md" %}
[prompt-guiding-explained.md](how-everything-works/prompt-guiding-explained.md)
{% endcontent-ref %}

## Great You're Ready to Make your first template!

```python
memory = """### Instruction
You are a creative agent roleplaying as a character called {bot_name}. Stay true to the persona given, reply with long and descriptive sentences.
Do not be repetitive.
This is {bot_name}'s persona: {memory}"""
prompt = "\n### Input:\n# {bot_name}'s example conversation:\n{prompt}\n# {bot_name}'s actual conversation:\n"


class CreativeFormatter(PromptFormatter):
    memory_template = memory
    prompt_template = prompt
    bot_template = "{bot_name}: {message}\n"
    user_template = "{user_name}: {message}\n"
    response_template = "### Response:\n{bot_name}:"
```

Simply submit your model using the chai package

{% tabs %}
{% tab title="Python" %}
```python
import chaiverse as chai

model_url = "AiForTheChurch/ChristianGPT-base-full-precision"

submission_parameters = {
	"model_repo": model_url,
	"generation_params": {
		"temperature": 0.99,
    "top_p": 0.2,
    "top_k": 40,
    "stopping_words": ['\n'],
    "presence_penalty": 0.,
    "frequency_penalty": 0.,
    "max_input_tokens": 1024,
    "best_of": 4
	},
  "formatter": CreativeFormatter(),
  'model_name': 'My-Christian-Model',
}
submitter = chai.ModelSubmitter(verbose=True)
submission_id = submitter.submit(submission_parameters)
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Currently, only 2 models are allowed to be deployed at a time.
{% endhint %}

{% content-ref url="deactivating-your-model.md" %}
[deactivating-your-model.md](deactivating-your-model.md)
{% endcontent-ref %}
