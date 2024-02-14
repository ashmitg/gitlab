---
description: Need to deactivate your model? You are at the perfect place!
---

# Deactivating your Model

## See your submissions by:

```
submission_ids = chai.get_my_submissions()
print(submission_ids)
```

## Deactivate a single model by

```
chai.deactivate_model(submission_id)
```

## Deactivate all your models

```
for sub_id, status in submission_ids.items():
    if status in ['deployed']:
        chai.deactivate_model(sub_id)
```



