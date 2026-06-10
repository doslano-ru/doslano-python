# PaymentResult


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**charged** | **bool** | Списаны ли средства с баланса. | 
**status** | **str** | &#x60;awaiting_payment&#x60; — при &#x60;on_insufficient_funds&#x3D;hold&#x60; до пополнения. | [optional] 

## Example

```python
from doslano.models.payment_result import PaymentResult

# TODO update the JSON string below
json = "{}"
# create an instance of PaymentResult from a JSON string
payment_result_instance = PaymentResult.from_json(json)
# print the JSON string representation of the object
print(PaymentResult.to_json())

# convert the object into a dict
payment_result_dict = payment_result_instance.to_dict()
# create an instance of PaymentResult from a dict
payment_result_from_dict = PaymentResult.from_dict(payment_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


