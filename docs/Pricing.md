# Pricing


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total_minor** | **int** | Итоговая списанная сумма, в копейках. | 
**currency** | **str** |  | 
**promo** | [**PromoResult**](PromoResult.md) |  | [optional] 

## Example

```python
from doslano.models.pricing import Pricing

# TODO update the JSON string below
json = "{}"
# create an instance of Pricing from a JSON string
pricing_instance = Pricing.from_json(json)
# print the JSON string representation of the object
print(Pricing.to_json())

# convert the object into a dict
pricing_dict = pricing_instance.to_dict()
# create an instance of Pricing from a dict
pricing_from_dict = Pricing.from_dict(pricing_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


