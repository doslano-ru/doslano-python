# LetterContent

Контент письма. Опись формируется автоматически.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**main_file** | [**FileSource**](FileSource.md) |  | 
**attachments** | [**List[FileSource]**](FileSource.md) |  | [optional] 

## Example

```python
from doslano.models.letter_content import LetterContent

# TODO update the JSON string below
json = "{}"
# create an instance of LetterContent from a JSON string
letter_content_instance = LetterContent.from_json(json)
# print the JSON string representation of the object
print(LetterContent.to_json())

# convert the object into a dict
letter_content_dict = letter_content_instance.to_dict()
# create an instance of LetterContent from a dict
letter_content_from_dict = LetterContent.from_dict(letter_content_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


