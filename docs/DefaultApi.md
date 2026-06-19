# doslano.DefaultApi

All URIs are relative to *https://integration.doslano.ru*

Method | HTTP request | Description
------------- | ------------- | -------------
[**on_letter_status_changed**](DefaultApi.md#on_letter_status_changed) | **POST** /letterStatusChanged | Колбек на финальный статус


# **on_letter_status_changed**
> on_letter_status_changed(webhook_event)

Колбек на финальный статус

Если при отправке письма указан `callback_url`, мы шлём на него POST при достижении финального статуса — по каждому получателю (`recipient.sent` / `recipient.failed`) и агрегатно по письму (`letter.sent` / `letter.partial_failure` / `letter.failed` / `letter.cancelled`).  Отдельный случай `letter.cancelled` — когда адрес/ФИО не прошли проверку Почты России **уже после** ответа `201` (поздний preflight: проверка не успела завершиться в окне синхронного ответа). Письмо отменяется автоматически, в `data.error` — перечень полей с ошибками; исправьте данные и создайте письмо заново. Если же ошибка адреса выявлена **сразу** при создании — вы получаете её синхронно (HTTP 422 `address_validation_failed`), и колбек по такому письму НЕ шлётся. То есть на одно письмо приходит ровно один сигнал об адресной ошибке: либо синхронный 422, либо асинхронный `letter.cancelled`.  **Подпись.** Заголовок `X-Doslano-Signature: t=<unix>,v1=<hex>` — где `v1 = HMAC_SHA256(secret, \"<t>.\" + raw_body)`, `secret` — секрет аккаунта из ЛК (раздел «API»). Проверьте подпись и свежесть `t` (±5 мин).  **Доставка.** At-least-once: ждём ответ `2xx`; иначе ретраим по нарастающему графику (несколько попыток в течение ~24 ч), затем помечаем как недоставленный (видно в ЛК, можно переотправить). Дедуп — по `id` события. Порядок не гарантируется — сверяйтесь со `status` в теле. 

### Example


```python
import doslano
from doslano.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://integration.doslano.ru
# See configuration.py for a list of all supported configuration parameters.
configuration = doslano.Configuration(
    host = "https://integration.doslano.ru"
)


# Enter a context with an instance of the API client
with doslano.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = doslano.DefaultApi(api_client)
    webhook_event = doslano.WebhookEvent() # WebhookEvent | 

    try:
        # Колбек на финальный статус
        api_instance.on_letter_status_changed(webhook_event)
    except Exception as e:
        print("Exception when calling DefaultApi->on_letter_status_changed: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **webhook_event** | [**WebhookEvent**](WebhookEvent.md)|  | 

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Принято (любой 2xx останавливает ретраи). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

