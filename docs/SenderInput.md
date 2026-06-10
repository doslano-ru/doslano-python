# SenderInput


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | ФИО или название отправителя. | 
**address** | **str** | Адрес отправителя (строкой; нормализуется на нашей стороне). | 
**email** | **str** |  | [optional] 
**party_type** | [**PartyType**](PartyType.md) |  | [optional] 
**inn** | **str** | ИНН (для юр. лиц/ИП). | [optional] 

## Example

```python
from doslano.models.sender_input import SenderInput

# TODO update the JSON string below
json = "{}"
# create an instance of SenderInput from a JSON string
sender_input_instance = SenderInput.from_json(json)
# print the JSON string representation of the object
print(SenderInput.to_json())

# convert the object into a dict
sender_input_dict = sender_input_instance.to_dict()
# create an instance of SenderInput from a dict
sender_input_from_dict = SenderInput.from_dict(sender_input_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


