# Recipient


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** |  | 
**name** | **str** |  | 
**address** | **str** |  | [optional] 
**status** | [**RecipientStatus**](RecipientStatus.md) |  | 
**shipment_number** | **str** | Наш трек-номер (РПО), присваивается сразу при создании. | [optional] 
**tracking_number** | **str** | Трек-номер Почты России (ШПИ). Появляется после регистрации отправления. | [optional] 
**price_minor** | **int** | Стоимость отправления этому получателю, в копейках. | [optional] 
**error** | **str** | Причина ошибки (для &#x60;failed&#x60;). | [optional] 

## Example

```python
from doslano.models.recipient import Recipient

# TODO update the JSON string below
json = "{}"
# create an instance of Recipient from a JSON string
recipient_instance = Recipient.from_json(json)
# print the JSON string representation of the object
print(Recipient.to_json())

# convert the object into a dict
recipient_dict = recipient_instance.to_dict()
# create an instance of Recipient from a dict
recipient_from_dict = Recipient.from_dict(recipient_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


