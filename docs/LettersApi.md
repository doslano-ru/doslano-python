# doslano.LettersApi

All URIs are relative to *https://integration.doslano.ru*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_letter**](LettersApi.md#create_letter) | **POST** /v1/letters | Отправить письмо
[**get_letter**](LettersApi.md#get_letter) | **GET** /v1/letters/{id} | Статус письма
[**get_recipient_tracking**](LettersApi.md#get_recipient_tracking) | **GET** /v1/letters/{id}/recipients/{recipient_id}/tracking | Трек-события получателя
[**list_letters**](LettersApi.md#list_letters) | **GET** /v1/letters | Список писем


# **create_letter**
> DryRunResult create_letter(create_letter_request, idempotency_key=idempotency_key)

Отправить письмо

Создаёт и (по умолчанию) сразу оплачивает с баланса одно заказное письмо одним запросом. Опись формируется автоматически на нашей стороне.  Требуется scope `letters:write`. 

### Example

* Bearer (API key) Authentication (apiKey):

```python
import doslano
from doslano.models.create_letter_request import CreateLetterRequest
from doslano.models.dry_run_result import DryRunResult
from doslano.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://integration.doslano.ru
# See configuration.py for a list of all supported configuration parameters.
configuration = doslano.Configuration(
    host = "https://integration.doslano.ru"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API key): apiKey
configuration = doslano.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with doslano.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = doslano.LettersApi(api_client)
    create_letter_request = {"sender":{"name":"ООО «Мой Бизнес»","party_type":"organization","inn":"7710000001","address":"101000, г Москва, Мясницкая ул, д 10","email":"claims@mybiz.example"},"recipients":[{"name":"ООО «Ромашка»","party_type":"organization","inn":"7707083893","resolve_address_by_inn":true},{"name":"Иванов Иван Иванович","party_type":"individual","address":"190000, г Санкт-Петербург, Невский пр-кт, д 1, кв 5"}],"content":{"main_file":{"url":"https://files.example.com/claim.pdf","filename":"Претензия.pdf"}}} # CreateLetterRequest | 
    idempotency_key = 'idempotency_key_example' # str | Ключ идемпотентности. Повтор с тем же ключом в течение TTL вернёт исходный результат, не создавая письмо повторно. (optional)

    try:
        # Отправить письмо
        api_response = api_instance.create_letter(create_letter_request, idempotency_key=idempotency_key)
        print("The response of LettersApi->create_letter:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LettersApi->create_letter: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **create_letter_request** | [**CreateLetterRequest**](CreateLetterRequest.md)|  | 
 **idempotency_key** | **str**| Ключ идемпотентности. Повтор с тем же ключом в течение TTL вернёт исходный результат, не создавая письмо повторно. | [optional] 

### Return type

[**DryRunResult**](DryRunResult.md)

### Authorization

[apiKey](../README.md#apiKey)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Письмо принято. Тело — состояние письма (включая цену и результат промокода). |  -  |
**200** | Пробный прогон (&#x60;dry_run: true&#x60;) успешен: запрос валиден, показан расчёт. Письмо не создано, средства не списаны. |  -  |
**400** | Некорректный запрос. |  -  |
**401** | Нет/неверный API-ключ, либо IP не в allowlist ключа. |  -  |
**403** | У ключа нет нужного scope. |  -  |
**402** | Недостаточно средств на балансе (при &#x60;on_insufficient_funds&#x3D;reject&#x60;). |  -  |
**422** | Ошибка валидации данных письма (адрес, файл, получатели и т.п.). В частности &#x60;code: address_validation_failed&#x60; — адрес/ФИО не прошли preflight-проверку Почты России: письмо отменено, в &#x60;detail&#x60; перечислены стороны и поля; исправьте данные и создайте письмо заново. Коды &#x60;recipient_address_unresolved&#x60; и &#x60;recipient_resolve_requires_inn&#x60; относятся к опции &#x60;resolve_address_by_inn&#x60; (см. RecipientInput). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_letter**
> Letter get_letter(id)

Статус письма

Полное состояние письма с разбивкой по получателям и трек-номерами. Требуется scope `letters:read`.

### Example

* Bearer (API key) Authentication (apiKey):

```python
import doslano
from doslano.models.letter import Letter
from doslano.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://integration.doslano.ru
# See configuration.py for a list of all supported configuration parameters.
configuration = doslano.Configuration(
    host = "https://integration.doslano.ru"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API key): apiKey
configuration = doslano.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with doslano.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = doslano.LettersApi(api_client)
    id = 'id_example' # str | Идентификатор письма.

    try:
        # Статус письма
        api_response = api_instance.get_letter(id)
        print("The response of LettersApi->get_letter:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LettersApi->get_letter: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| Идентификатор письма. | 

### Return type

[**Letter**](Letter.md)

### Authorization

[apiKey](../README.md#apiKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Состояние письма. |  -  |
**401** | Нет/неверный API-ключ, либо IP не в allowlist ключа. |  -  |
**403** | У ключа нет нужного scope. |  -  |
**404** | Ресурс не найден (или не принадлежит аккаунту). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_recipient_tracking**
> TrackingInfo get_recipient_tracking(id, recipient_id)

Трек-события получателя

События трекинга Почты России по конкретному получателю (если трек-номер присвоен). Требуется scope `letters:read`.

### Example

* Bearer (API key) Authentication (apiKey):

```python
import doslano
from doslano.models.tracking_info import TrackingInfo
from doslano.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://integration.doslano.ru
# See configuration.py for a list of all supported configuration parameters.
configuration = doslano.Configuration(
    host = "https://integration.doslano.ru"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API key): apiKey
configuration = doslano.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with doslano.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = doslano.LettersApi(api_client)
    id = 'id_example' # str | Идентификатор письма.
    recipient_id = 'recipient_id_example' # str | 

    try:
        # Трек-события получателя
        api_response = api_instance.get_recipient_tracking(id, recipient_id)
        print("The response of LettersApi->get_recipient_tracking:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LettersApi->get_recipient_tracking: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| Идентификатор письма. | 
 **recipient_id** | **str**|  | 

### Return type

[**TrackingInfo**](TrackingInfo.md)

### Authorization

[apiKey](../README.md#apiKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | События трекинга. |  -  |
**401** | Нет/неверный API-ключ, либо IP не в allowlist ключа. |  -  |
**403** | У ключа нет нужного scope. |  -  |
**404** | Ресурс не найден (или не принадлежит аккаунту). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_letters**
> ListLetters200Response list_letters(limit=limit, offset=offset, status=status, created_from=created_from, created_to=created_to)

Список писем

Письма аккаунта (все каналы — и API, и личный кабинет; канал указан в поле `channel`). Требуется scope `letters:read`.

### Example

* Bearer (API key) Authentication (apiKey):

```python
import doslano
from doslano.models.letter_status import LetterStatus
from doslano.models.list_letters200_response import ListLetters200Response
from doslano.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://integration.doslano.ru
# See configuration.py for a list of all supported configuration parameters.
configuration = doslano.Configuration(
    host = "https://integration.doslano.ru"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API key): apiKey
configuration = doslano.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with doslano.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = doslano.LettersApi(api_client)
    limit = 20 # int |  (optional) (default to 20)
    offset = 0 # int |  (optional) (default to 0)
    status = doslano.LetterStatus() # LetterStatus |  (optional)
    created_from = '2013-10-20T19:20:30+01:00' # datetime |  (optional)
    created_to = '2013-10-20T19:20:30+01:00' # datetime |  (optional)

    try:
        # Список писем
        api_response = api_instance.list_letters(limit=limit, offset=offset, status=status, created_from=created_from, created_to=created_to)
        print("The response of LettersApi->list_letters:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling LettersApi->list_letters: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**|  | [optional] [default to 20]
 **offset** | **int**|  | [optional] [default to 0]
 **status** | [**LetterStatus**](.md)|  | [optional] 
 **created_from** | **datetime**|  | [optional] 
 **created_to** | **datetime**|  | [optional] 

### Return type

[**ListLetters200Response**](ListLetters200Response.md)

### Authorization

[apiKey](../README.md#apiKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Страница писем. |  -  |
**401** | Нет/неверный API-ключ, либо IP не в allowlist ключа. |  -  |
**403** | У ключа нет нужного scope. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

