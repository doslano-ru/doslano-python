# Letter


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** |  | 
**channel** | **str** | Канал создания письма — &#x60;api&#x60; (этот API) или &#x60;web&#x60; (личный кабинет). | 
**status** | [**LetterStatus**](LetterStatus.md) |  | 
**created_at** | **datetime** |  | 
**sender** | [**Party**](Party.md) |  | [optional] 
**recipients** | [**List[Recipient]**](Recipient.md) |  | 
**pricing** | [**Pricing**](Pricing.md) |  | 
**payment** | [**PaymentResult**](PaymentResult.md) |  | [optional] 
**callback_url** | **str** |  | [optional] 

## Example

```python
from doslano.models.letter import Letter

# TODO update the JSON string below
json = "{}"
# create an instance of Letter from a JSON string
letter_instance = Letter.from_json(json)
# print the JSON string representation of the object
print(Letter.to_json())

# convert the object into a dict
letter_dict = letter_instance.to_dict()
# create an instance of Letter from a dict
letter_from_dict = Letter.from_dict(letter_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


