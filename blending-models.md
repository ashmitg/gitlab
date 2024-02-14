---
description: Blending models has proven to significantly improve performance
---

# Blending Models

In-depth explanation

{% embed url="https://arxiv.org/abs/2401.02994" %}

## Submit the blended model

After importing the chaiverse package, you may submit the blend

{% tabs %}
{% tab title="Python" %}
```
import chaiverse as chai
submitter = chai.ModelSubmitter(verbose=True)

// submit the blended model
submissions_to_blend = ["submission1_id", "submission2_id", "submission3_id"]
blend_id = submitter.submit_blend({"submissions": submissions_to_blend, "model_name": "my-blended-model"})
```
{% endtab %}
{% endtabs %}



{% hint style="info" %}
Currently, only 2 total models are allowed to be deployed at a time
{% endhint %}

{% content-ref url="deactivating-your-model.md" %}
[deactivating-your-model.md](deactivating-your-model.md)
{% endcontent-ref %}
