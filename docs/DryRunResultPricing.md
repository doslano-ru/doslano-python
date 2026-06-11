# DryRunResultPricing

Расчёт к списанию при реальной отправке этого запроса.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**subtotal_minor** | **int** | Цена без скидки, в копейках. | 
**total_minor** | **int** | Итог к списанию (после промокода), в копейках. Non-binding — фиксируется при реальной оплате. | 
**currency** | **str** |  | 
**promo** | [**PromoResult**](PromoResult.md) |  | [optional] 

## Example

```python
from doslano.models.dry_run_result_pricing import DryRunResultPricing

# TODO update the JSON string below
json = "{}"
# create an instance of DryRunResultPricing from a JSON string
dry_run_result_pricing_instance = DryRunResultPricing.from_json(json)
# print the JSON string representation of the object
print(DryRunResultPricing.to_json())

# convert the object into a dict
dry_run_result_pricing_dict = dry_run_result_pricing_instance.to_dict()
# create an instance of DryRunResultPricing from a dict
dry_run_result_pricing_from_dict = DryRunResultPricing.from_dict(dry_run_result_pricing_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


