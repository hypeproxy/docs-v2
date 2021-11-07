---
description: How to place orders with our API.
---

# Order Process

Our order process is divided into two phases, the first consists of validating the order according to a defined model such as a type of product, a desired location, a quantity etc. and the second is the purchasing.

{% swagger baseUrl="https://api.hypeproxy.io" path="/v2/orders/validate" method="post" summary="Order Validation" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="productId" type="string" %}
The Product Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="locationId" type="string" %}
The Location Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="quantity" type="number" %}
The quantity of products to buy
{% endswagger-parameter %}

{% swagger-parameter in="body" name="billingPeriod" type="string" %}
Monthly, Weekly, Daily, or Yearly
{% endswagger-parameter %}

{% swagger-parameter in="body" name="IsAutoRenewed" type="string" %}
If the order will be renewed each months (only available with credit card payments).
{% endswagger-parameter %}

{% swagger-parameter in="body" name="couponCode" type="string" %}
The coupon code if you have anyone.
{% endswagger-parameter %}

{% swagger-response status="200" description="The API return if the validation is passed or not, which errors was thrown if the validation failed and also the price to pay." %}
```javascript
{
	"message": "Validation Passed. You can now use /v2/Orders endpoint to create an order.",
	"statusCode": "OK",
	"requestDetails": {
		"userId": "3920eca8-5001-4f6e-b9cf-63328cd654b5",
		"endpoint": "/v2/Orders/Validate",
		"date": "2021-07-01T13:54:10.77788Z",
		"timestamp": 1625147650,
		"userAgent": "Paw/3.2.2 (Macintosh; OS X/11.4.0)",
		"clientIp": "158.28.190.23"
	},
	"data": {
		"price": {
			"unitPrice": 14.0,
			"totalPrice": 25.2,
			"priceOff": 2.8000000000000003
		}
	}
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Validation Failed, not enough stock available." %}
```javascript
{
	"errors": [
		{
			"message": "Insufficient quantity available for this kind of products/locations.",
			"code": "InsufficientQuantityAvailable"
		}
	],
	"message": "Request Failed",
	"statusCode": "BadRequest",
	"requestDetails": {
		"userId": "3920eca8-5001-4f6e-b9cf-63328cd654b5",
		"endpoint": "/v2/Orders/Validate",
		"date": "2021-07-01T13:54:10.77788Z",
		"timestamp": 1625147650,
		"userAgent": "Paw/3.2.2 (Macintosh; OS X/11.4.0)",
		"clientIp": "127.0.0.1"
	},
	"data": {
		"price": {
			"unitPrice": 14.0,
			"totalPrice": 50.4,
			"priceOff": 5.6000000000000005
		}
	}
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://api.hypeproxy.io" path="/v2/orders" method="post" summary="Order Creation" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="" type="string" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}
