# TrackingInfoEventsInner


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**code** | **str** |  | [optional] 
**name** | **str** |  | [optional] 
**occurred_at** | **datetime** |  | [optional] 
**location** | **str** |  | [optional] 

## Example

```python
from doslano.models.tracking_info_events_inner import TrackingInfoEventsInner

# TODO update the JSON string below
json = "{}"
# create an instance of TrackingInfoEventsInner from a JSON string
tracking_info_events_inner_instance = TrackingInfoEventsInner.from_json(json)
# print the JSON string representation of the object
print(TrackingInfoEventsInner.to_json())

# convert the object into a dict
tracking_info_events_inner_dict = tracking_info_events_inner_instance.to_dict()
# create an instance of TrackingInfoEventsInner from a dict
tracking_info_events_inner_from_dict = TrackingInfoEventsInner.from_dict(tracking_info_events_inner_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


