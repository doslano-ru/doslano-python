# TrackingInfo


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**recipient_id** | **str** |  | 
**shipment_number** | **str** |  | [optional] 
**tracking_number** | **str** |  | [optional] 
**events** | [**List[TrackingInfoEventsInner]**](TrackingInfoEventsInner.md) |  | 

## Example

```python
from doslano.models.tracking_info import TrackingInfo

# TODO update the JSON string below
json = "{}"
# create an instance of TrackingInfo from a JSON string
tracking_info_instance = TrackingInfo.from_json(json)
# print the JSON string representation of the object
print(TrackingInfo.to_json())

# convert the object into a dict
tracking_info_dict = tracking_info_instance.to_dict()
# create an instance of TrackingInfo from a dict
tracking_info_from_dict = TrackingInfo.from_dict(tracking_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


