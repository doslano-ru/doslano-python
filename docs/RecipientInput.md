# RecipientInput


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | ФИО или название получателя. При resolve_address_by_inn&#x3D;true ПЕРЕЗАПИСЫВАЕТСЯ наименованием из ЕГРЮЛ. | 
**address** | **str** | Адрес получателя (строкой; нормализуется на нашей стороне). Можно опустить при resolve_address_by_inn&#x3D;true. | [optional] 
**party_type** | [**PartyType**](PartyType.md) |  | [optional] 
**inn** | **str** |  | [optional] 
**resolve_address_by_inn** | **bool** | Авто-резолв адреса по ИНН из ЕГРЮЛ. Работает только для party_type&#x3D;organization с заданным inn: адрес и наименование берутся из реестра (DaData findById/party, головная организация), address можно не передавать. Если резолв не удался и address не передан — 422 recipient_address_unresolved; флаг без inn или не для organization — 422 recipient_resolve_requires_inn. Если передан и address — он fallback при неудаче резолва. | [optional] [default to False]

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


