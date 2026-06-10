# doslano.BalanceApi

All URIs are relative to *https://integration.doslano.ru*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_balance**](BalanceApi.md#get_balance) | **GET** /v1/balance | Баланс аккаунта


# **get_balance**
> Balance get_balance()

Баланс аккаунта

Текущий баланс в копейках. Требуется scope `balance:read`.

### Example

* Bearer (API key) Authentication (apiKey):

```python
import doslano
from doslano.models.balance import Balance
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
    api_instance = doslano.BalanceApi(api_client)

    try:
        # Баланс аккаунта
        api_response = api_instance.get_balance()
        print("The response of BalanceApi->get_balance:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling BalanceApi->get_balance: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**Balance**](Balance.md)

### Authorization

[apiKey](../README.md#apiKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Баланс. |  -  |
**401** | Нет/неверный API-ключ, либо IP не в allowlist ключа. |  -  |
**403** | У ключа нет нужного scope. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

