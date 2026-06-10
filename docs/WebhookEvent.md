# WebhookEvent


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Уникальный идентификатор события (для дедупа). | 
**type** | **str** |  | 
**created_at** | **datetime** |  | 
**data** | [**WebhookEventData**](WebhookEventData.md) |  | 

## Example

```python
from doslano.models.webhook_event import WebhookEvent

# TODO update the JSON string below
json = "{}"
# create an instance of WebhookEvent from a JSON string
webhook_event_instance = WebhookEvent.from_json(json)
# print the JSON string representation of the object
print(WebhookEvent.to_json())

# convert the object into a dict
webhook_event_dict = webhook_event_instance.to_dict()
# create an instance of WebhookEvent from a dict
webhook_event_from_dict = WebhookEvent.from_dict(webhook_event_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


