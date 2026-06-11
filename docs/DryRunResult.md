# DryRunResult

Результат пробного прогона (`dry_run: true`): запрос полностью валиден. Письмо НЕ создано, средства НЕ списаны. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**dry_run** | **bool** | Всегда &#x60;true&#x60; (маркер ответа пробного прогона). | 
**valid** | **bool** | Всегда &#x60;true&#x60; — невалидные запросы получают 400/422. | 
**recipients_count** | **int** | Количество получателей (&#x3D; отправлений) в запросе. | 
**pricing** | [**DryRunResultPricing**](DryRunResultPricing.md) |  | 

## Example

```python
from doslano.models.dry_run_result import DryRunResult

# TODO update the JSON string below
json = "{}"
# create an instance of DryRunResult from a JSON string
dry_run_result_instance = DryRunResult.from_json(json)
# print the JSON string representation of the object
print(DryRunResult.to_json())

# convert the object into a dict
dry_run_result_dict = dry_run_result_instance.to_dict()
# create an instance of DryRunResult from a dict
dry_run_result_from_dict = DryRunResult.from_dict(dry_run_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


