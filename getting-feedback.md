---
description: This is everything you need to know about receiving feedback on your model
---

# Getting Feedback

{% hint style="info" %}
**Good to know:** Receiving feedback is essential to building a great model and iterating on feedback
{% endhint %}

Get sample responses from your deployed model

{% tabs %}
{% tab title="Python" %}
```
fb = chai.get_feedback(submission_id)
fb.sample() #shall return a sample
```
{% endtab %}
{% endtabs %}

## Get model stats, ie (stays\_in\_character, safety score, etc)

{% tabs %}
{% tab title="Python" %}
```python
chai.get_model_info(submission_id)
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Please Note: It may take 10-15 minutes for your model to receive these stats
{% endhint %}
