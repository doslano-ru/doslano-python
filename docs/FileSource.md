# FileSource

Источник PDF-файла. Укажите **ровно один** способ: - `base64` — содержимое файла в base64 (для небольших файлов); - `url` — HTTPS-ссылка, файл скачивается потоково (для крупных файлов,   чтобы не передавать тело в base64). Лимиты по размеру/страницам — см. документацию; тип файла — только PDF. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**var_base64** | **str** | PDF в base64. | [optional] 
**url** | **str** | HTTPS-ссылка на PDF (скачиваем потоково). | [optional] 
**filename** | **str** | Имя файла (опционально, для отображения). | [optional] 

## Example

```python
from doslano.models.file_source import FileSource

# TODO update the JSON string below
json = "{}"
# create an instance of FileSource from a JSON string
file_source_instance = FileSource.from_json(json)
# print the JSON string representation of the object
print(FileSource.to_json())

# convert the object into a dict
file_source_dict = file_source_instance.to_dict()
# create an instance of FileSource from a dict
file_source_from_dict = FileSource.from_dict(file_source_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


