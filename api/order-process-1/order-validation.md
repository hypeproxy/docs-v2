# Order Validation

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum

{% swagger method="post" path="/Orders/Validate" baseUrl="https://api.hypeproxy.io/v2" summary="Validate an order model and return if the order is possible or not." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" required="true" name="productId" type="Guid" %}
Product Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="locationId" required="true" type="Guid" %}
Location Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="billingPeriod" required="true" type="Enum" %}
`Daily`

, 

`Weekly`

, 

`Monthly`

 or 

`Yearly`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMethod" required="true" type="Enum" %}
`CreditCard`

 or 

`Cryptos`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="quantity" required="true" type="Integer" %}
Quantity, like 1, 2, 3, 10 etc
{% endswagger-parameter %}

{% swagger-parameter in="body" name="isAutoRenewed" required="true" type="Boolean" %}
If payment should be renewed every end of billing period.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="couponCode" type="String" %}
If you have a coupon code you can put it there.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Validation passed response" %}
```javascript
{
    "message": "Validation Passed. You can now use /v2/Orders endpoint to create an order.",
    "statusCode": "OK",
    "requestDetails": {
        "userId": "00000000-0000-0000-0000-000000000000",
        "endpoint": "/v2/Orders/Validate",
        "date": "2021-11-07T15:01:06.776251Z",
        "timestamp": 1636297266,
        "userAgent": "PostmanRuntime/7.28.4",
        "clientIp": "::1"
    },
    "data": {
        "price": {
            "unitPrice": 55,
            "totalPrice": 55
        }
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Insufficient quantity available for this kind of products/locations." %}
```javascript
{
    "errors": [
        {
            "code": "InsufficientQuantityAvailable",
            "message": "Insufficient quantity available for this kind of products/locations."
        }
    ],
    "message": "Request failed.",
    "statusCode": "BadRequest",
    "requestDetails": {
        "userId": "00000000-0000-0000-0000-000000000000",
        "endpoint": "/v2/Orders/Validate",
        "date": "2021-11-07T15:02:02.753931Z",
        "timestamp": 1636297322,
        "userAgent": "PostmanRuntime/7.28.4",
        "clientIp": "::1"
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Payment autorenew not possible with this payment method." %}
```javascript
{
    "errors": [
        {
            "code": "UnavailableAutomaticRenew",
            "message": "With this payment method it's not possible to enable autorenew."
        }
    ],
    "message": "Request failed.",
    "statusCode": "BadRequest",
    "requestDetails": {
        "userId": "00000000-0000-0000-0000-000000000000",
        "endpoint": "/v2/Orders/Validate",
        "date": "2021-11-07T15:04:15.939415Z",
        "timestamp": 1636297455,
        "userAgent": "PostmanRuntime/7.28.4",
        "clientIp": "::1"
    }
}
```
{% endswagger-response %}
{% endswagger %}





