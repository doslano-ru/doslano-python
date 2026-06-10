# CreateLetterRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**sender** | [**SenderInput**](SenderInput.md) | Отправитель. Если не указан — берётся отправитель по умолчанию из профиля аккаунта. | [optional] 
**recipients** | [**List[RecipientInput]**](RecipientInput.md) |  | 
**content** | [**LetterContent**](LetterContent.md) |  | 
**letter_class** | [**LetterClass**](LetterClass.md) |  | [optional] [default to LetterClass.REGISTERED]
**promo_code** | **str** | Промокод (опционально). | [optional] 
**on_promo_invalid** | **str** | Что делать, если промокод не применился: &#x60;ignore&#x60; — отправить без скидки и вернуть пометку в &#x60;pricing.promo&#x60;; &#x60;reject&#x60; — отклонить (422).  | [optional] [default to 'ignore']
**on_insufficient_funds** | **str** | Что делать при нехватке средств: &#x60;reject&#x60; — отклонить (402), письмо не создаётся; &#x60;hold&#x60; — создать письмо в статусе &#x60;awaiting_payment&#x60;, оно оплатится автоматически при пополнении баланса.  | [optional] [default to 'reject']
**callback_url** | **str** | HTTPS-URL для колбеков по этому письму. Если не указан — используйте поллинг. | [optional] 

## Example

```python
from doslano.models.create_letter_request import CreateLetterRequest

# TODO update the JSON string below
json = "{}"
# create an instance of CreateLetterRequest from a JSON string
create_letter_request_instance = CreateLetterRequest.from_json(json)
# print the JSON string representation of the object
print(CreateLetterRequest.to_json())

# convert the object into a dict
create_letter_request_dict = create_letter_request_instance.to_dict()
# create an instance of CreateLetterRequest from a dict
create_letter_request_from_dict = CreateLetterRequest.from_dict(create_letter_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


