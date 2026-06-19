# Problem

Ошибка в формате RFC 9457 (problem+json).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **str** |  | [optional] 
**title** | **str** |  | [optional] 
**status** | **int** |  | [optional] 
**detail** | **str** |  | [optional] 
**code** | **str** | Машиночитаемый код ошибки (напр. &#x60;insufficient_funds&#x60;, &#x60;validation_failed&#x60;, &#x60;address_validation_failed&#x60;, &#x60;forbidden_scope&#x60;). | [optional] 

## Example

```python
from doslano.models.problem import Problem

# TODO update the JSON string below
json = "{}"
# create an instance of Problem from a JSON string
problem_instance = Problem.from_json(json)
# print the JSON string representation of the object
print(Problem.to_json())

# convert the object into a dict
problem_dict = problem_instance.to_dict()
# create an instance of Problem from a dict
problem_from_dict = Problem.from_dict(problem_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


