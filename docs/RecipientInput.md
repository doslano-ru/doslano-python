# RecipientInput


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | ФИО или название получателя. | 
**address** | **str** | Адрес получателя (строкой; нормализуется на нашей стороне). | 
**party_type** | [**PartyType**](PartyType.md) |  | [optional] 
**inn** | **str** |  | [optional] 

## Example

```python
from doslano.models.recipient_input import RecipientInput

# TODO update the JSON string below
json = "{}"
# create an instance of RecipientInput from a JSON string
recipient_input_instance = RecipientInput.from_json(json)
# print the JSON string representation of the object
print(RecipientInput.to_json())

# convert the object into a dict
recipient_input_dict = recipient_input_instance.to_dict()
# create an instance of RecipientInput from a dict
recipient_input_from_dict = RecipientInput.from_dict(recipient_input_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


