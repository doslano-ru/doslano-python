# PromoResult

Результат применения промокода (если передан).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**code** | **str** |  | 
**applied** | **bool** | Применён ли промокод. | 
**discount_minor** | **int** | Размер скидки в копейках (если применён). | [optional] 
**message** | **str** | Пояснение, если промокод не применён (письмо при этом отправлено). | [optional] 

## Example

```python
from doslano.models.promo_result import PromoResult

# TODO update the JSON string below
json = "{}"
# create an instance of PromoResult from a JSON string
promo_result_instance = PromoResult.from_json(json)
# print the JSON string representation of the object
print(PromoResult.to_json())

# convert the object into a dict
promo_result_dict = promo_result_instance.to_dict()
# create an instance of PromoResult from a dict
promo_result_from_dict = PromoResult.from_dict(promo_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


