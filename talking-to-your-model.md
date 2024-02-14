---
description: Wanna chat with your model?
---

# Talking to your model

Using your submission\_id, you can:

## Choose from any of these characters to chat with

1. blade
2. captain\_wyatt
3. coffee\_shop\_girl
4. filbert
5. leo
6. levi
7. mr\_wilson
8. nerd\_girl
9. scaramouche
10. story\_teller
11. vampire\_queen
12. wednesday\_addams

## Begin your conversation using the Chai module

{% tabs %}
{% tab title="Python" %}
```
submission_id = 'user-example_v1'
chatbot = chai.SubmissionChatbot(submission_id)
chatbot.chat('vampire_queen', show_model_input=True)
```
{% endtab %}
{% endtabs %}

## You may also chat with your bot on discord #chat-with-ai

{% embed url="https://discord.gg/chai-llm" %}
Join the cord!
{% endembed %}
