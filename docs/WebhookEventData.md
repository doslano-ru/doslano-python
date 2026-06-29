# WebhookEventData


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**letter_id** | **str** |  | 
**recipient_id** | **str** |  | [optional] 
**status** | **str** |  | 
**shipment_number** | **str** |  | [optional] 
**tracking_number** | **str** |  | [optional] 
**error** | **str** |  | [optional] 
**amount_minor** | **int** | Фактически списанная стоимость отправления ЭТОМУ получателю, в копейках (доля дисконтированного тотала письма с учётом промокода). Присутствует только в &#x60;recipient.sent&#x60; — отправление реально ушло и оплачено. В &#x60;recipient.failed&#x60; отсутствует: при провале сумма возвращается на баланс. | [optional] 
**receipt_pdf** | **str** | Ссылка на скачивание PDF фискального чека (54-ФЗ) через наш API. Колбэк &#x60;recipient.sent&#x60; уходит ПОСЛЕ готовности чека, поэтому поле в нём присутствует (вместе с &#x60;receipt_url&#x60;). | [optional] 
**receipt_url** | **str** | Ссылка на фискальный чек на сайте ОФД (1-ОФД). Может присутствовать и без &#x60;receipt_pdf&#x60; (link_only — наш PDF недоступен). | [optional] 
**inventory_pdf** | **str** | Ссылка на скачивание PDF описи вложения (форма 107, версия отправителя) через наш API. Присутствует в &#x60;recipient.sent&#x60; и &#x60;recipient.delivered&#x60;, когда опись сформирована. | [optional] 

## Example

```python
from doslano.models.webhook_event_data import WebhookEventData

# TODO update the JSON string below
json = "{}"
# create an instance of WebhookEventData from a JSON string
webhook_event_data_instance = WebhookEventData.from_json(json)
# print the JSON string representation of the object
print(WebhookEventData.to_json())

# convert the object into a dict
webhook_event_data_dict = webhook_event_data_instance.to_dict()
# create an instance of WebhookEventData from a dict
webhook_event_data_from_dict = WebhookEventData.from_dict(webhook_event_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


