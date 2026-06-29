# SenderInput

Отправитель. Любое поле можно опустить — оно берётся из профиля аккаунта (ЛК). Например, передайте только `email`, чтобы переопределить почту плательщика для кассового чека, а имя/адрес оставить из профиля. Если `sender` не передан целиком — весь отправитель берётся из профиля.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | ФИО или название отправителя. Не указано — из профиля ЛК. | [optional] 
**address** | **str** | Адрес отправителя (строкой; нормализуется). Не указан — из профиля ЛК. | [optional] 
**email** | **str** | Email отправителя (плательщика) для кассового чека. Не указан — из профиля ЛК. | [optional] 
**party_type** | [**PartyType**](PartyType.md) |  | [optional] 
**inn** | **str** | ИНН (для юр. лиц/ИП). Не указан — из профиля ЛК. | [optional] 

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


