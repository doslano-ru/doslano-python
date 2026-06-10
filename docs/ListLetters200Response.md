# ListLetters200Response


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[Letter]**](Letter.md) |  | 
**has_more** | **bool** |  | 

## Example

```python
from doslano.models.list_letters200_response import ListLetters200Response

# TODO update the JSON string below
json = "{}"
# create an instance of ListLetters200Response from a JSON string
list_letters200_response_instance = ListLetters200Response.from_json(json)
# print the JSON string representation of the object
print(ListLetters200Response.to_json())

# convert the object into a dict
list_letters200_response_dict = list_letters200_response_instance.to_dict()
# create an instance of ListLetters200Response from a dict
list_letters200_response_from_dict = ListLetters200Response.from_dict(list_letters200_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


