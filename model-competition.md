---
description: >-
  Your models are then put in a competition round where you will be evaluated
  based on user feedback
---

# 🤑 Model Competition

{% hint style="info" %}
Participants will be allowed to deploy 2 models for the competition round
{% endhint %}

## Enroll your models by:

```
chai.enroll_submission('MY_SUBMISSION_ID')
```

## Withdraw your submission

```
chai.withdraw_submission('submission_id')
```

## View Competition Submissions

```
competitions[0].enrolled_submission_ids
```

## See your spot in the competition Leaderboard

{% tabs %}
{% tab title="Python" %}
```
df = chai.display_competition_leaderboard(leaderboard_format='user_score_with_thumbs_up', regenerate=True)
```
{% endtab %}
{% endtabs %}

## Cooler version of the Competition leaderboard

{% embed url="https://leaderboard.serveo.net/" %}





