---
description: Reward Modelling is an essential part of making high-quality models.
---

# Rewards model

{% embed url="https://colab.research.google.com/drive/15lWzRoP0RZ7jVxhas_zQaG2OyvqxaxhT#scrollTo=u9nZ2-UeQiyl" %}
Notebook to submit rewards model
{% endembed %}

Now, you will have to install the chaiverse package to submit your first model

{% tabs %}
{% tab title="Python" %}
```
import chaiverse as chai
from chaiverse.formatters import PromptFormatter
```
{% endtab %}
{% endtabs %}

## How it works

{% content-ref url="how-everything-works/rewards-model-explained.md" %}
[rewards-model-explained.md](how-everything-works/rewards-model-explained.md)
{% endcontent-ref %}

## Great You're Ready to Submit your first rewards model



```python
model_url = "ChaiML/phase2_winner_13b2"
reward_url = "ChaiML/reward_models_100_170000000_cp_498032"

submission_parameters = {
	"model_repo": model_url,
  "reward_repo": reward_url,
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
  'model_name': 'My-First-RwardModel',
}
```

Simply submit your model using the chai package

{% tabs %}
{% tab title="Python" %}
```python
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
