---
description: 'Chaiverse: Reward Model Submission'
---

# Rewards Model Explained

* **Reward Modelling** is an essential part of making high-quality models.
* Best-of-N sampling is the main part of InstructGPT loop
* In fact, if you read the OpenAI's paper carefully, PPO out-of-the-box only achieves best-of-2 performance!
* Contrary to PPO (Proximal Policy Optimization), Best-of-N sampling is **simple**, **robust** and **high-performant**

{% embed url="https://arxiv.org/pdf/2303.06135.pdf" %}
In depth explanation
{% endembed %}

**Figure below shows the architecture for best-of-4 sampling with reward**

<figure><img src="../.gitbook/assets/download.png" alt=""><figcaption></figcaption></figure>

## Keep in mind these parameters

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
