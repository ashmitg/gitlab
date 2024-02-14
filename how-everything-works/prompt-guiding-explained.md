---
description: Everything you need to know about prompt guiding
---

# Prompt Guiding Explained

## Chaiverse: Prompting & Parameters Tuning Guide 🚀

* **Prompt Engineering** is an essential part of making high-quality models.
* The **Chaiverse** package provides competitors a easy interface for submitting models with custom prompts.
* Different from AI-Assistants, your model will be driving millions of characters, each with their own personas and prompts. This demo will explain what are the key variables and how they are used.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

### High-Level Overview of Chai Characters 😍

#### Definition

* There are \~5 million characters that are user-generated on the [Chai App](https://colab.research.google.com/corgiredirector?site=https%3A%2F%2Fapps.apple.com%2Fus%2Fapp%2Fchai-chat-with-ai-bots%2Fid1544750895)
* Your model will be the "engine" which drives the conversations between these characters and users
* Each character is defined by the following three things:
  * Character Name (`bot_name`): name of the character
  * Character Persona (`memory`): character's personalities
  * Example Conversation (`prompt`): character creator's provided example conversation

The illustration below shows both the app and the definition for a character on the app, which your model sees.

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

#### Context Window & Persistence 🪟

Given a fixed context window (the default is 512 tokens):

* We want the model to constantly remember the character's persona, hence it is **always** present within the context-window and it is called `memory`
* Example conversation matters less as the conversation evolves. As a result, it gets truncated as the **actual** conversation grows

#### Truncation

Intuitively, if the memory (i.e. character's persona) is too long, we should keep the first part, ignoring (thus truncation) the final parts.

If the prompt (i.e. example conversation) is too long, we should remove the top parts of the conversation, as the later part might be most relevant.

Therefore:

* If the `memory` is too long, it is truncated **FROM THE RIGHT**
* Whereas `prompt` is truncated **FROM THE LEFT**

In practice, the `memory` must not exceed over 1/2 the size of the context window. Truncation will be applied if any given character's `memory` exceeds this limit.

{% embed url="https://imgur.com/maWBg6B.gif" %}

## Essentially this is what your model will see

> ```
> ### Instruction:
> Her real name is Selena, she lives in a majestic castle, she is cold, she is kind, she is like a mother to you, she can be rude if you do not respect her.
> ### Input:
> # Example conversation
> Vampire Queen: *You wake up in a castle, tied up with roses, you hear footsteps….*
> User: Hello? Whos there? *scared*
> Vampire Queen: *A mysterious and majestic figure appears suddenly behind you* Hey, don’t worry, I wont hurt you. My name is Selena. *She unties you* What do you want?
> User: Em *shocked and scared* Why am I here? Can you untie me?
> Vampire Queen: Sure *she unties you* I saw you passed out in the woods, didn’t know what to do with you or whether you a threat so …. I did what I had to do.
> # Actual conversation:
> Vampire Queen: *You wake up in a castle, tied up with roses, you hear footsteps….*
> User: *struggles to untie myself* WHO ARE YOU!
> ### Response:
> Vampire Queen:
> ```
