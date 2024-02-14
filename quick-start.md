---
description: >-
  The basic overview of getting familiar with chaiverse and submitting your
  first model
---

# Quick Start

{% embed url="https://colab.research.google.com/drive/1FyCamT6icUo5Wlt6qqogHbyREHQQkAY8?usp=sharing" %}
Submit a model in < 10 minutes with Chaiverse Jupyter Notebook Quickstart
{% endembed %}

## Get your Dev Key

Please check your dm when your join discord.gg/chai-llm to get your key!

## Install the library

Now, you will have to install the chaiverse package to submit your first model

{% tabs %}
{% tab title="Python" %}
```
# Install via pip
pip install chaiverse
import chaiverse as chai
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
**Good to know:** You may need to install pydantic==1.10.8 if importing chaiverse throws an error
{% endhint %}

## Now you must authenticate yourself



```python
chai.developer_login('your_token')
```

## Great You're Ready to Submit your first Model!

Simply submit your model using the chai package

{% tabs %}
{% tab title="Python" %}
```python
import chaiverse as chai

model_url = "ChaiML/phase2_winner_13b2" # Your model URL

generation_params = {
    'temperature': 0.99,
    'top_p': 0.2,
    "top_k": 40,
    "stopping_words": ['\n'],
    "presence_penalty": 0.5,
    "frequency_penalty": 0.5,
    "max_input_tokens": 1024,
    "best_of": 4
    }
submission_parameters = {'model_repo': model_url, 'generation_params': generation_params, 'model_name': 'my-awesome-llama'}

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

## Great now you're ready to move on!
