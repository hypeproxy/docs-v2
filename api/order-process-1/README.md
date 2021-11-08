---
description: How order on HypeProxy.io using the API?
---

# Order Process

## Introduction

Our payment process is split into two steps, the first step for validation and the second step for order creation, both endpoints use basically same [JSON](https://www.json.org/json-en.html) model.

Our order process is divided into two phases, the first consists of validating the order according to a defined model such as a type of product, a desired location, a quantity etc. and the second is the purchasing.

Here are the two related endpoints:

```
/v2/Orders/Create
/v2/Orders/Validate
```

## What to Send?

Both of endpoints take the same JSON model, containing these properties:

* **Product Id**: Which [Product](broken-reference) you want to order.
* **Location Id**: In which [Location](broken-reference) you want to order.
* **Payment Method**: Define the payment method to use (Credit Card or Cryptocurrencies)
* **Billing Period**: Define the payment term of the order (Like Month, Week or Year)
* **Quantity**: How many products do you want to order?&#x20;
* **Is Auto Renewed**: Define if you want to automatically renew your order (subscription)
* **\[Optional] Coupon Code** Indicates a discount coupon to be used when ordering.

## Model Example:

Here is an example of the JSON model you should send:

```json
{
    "productId": "7d8f2363-2fc9-47af-aae2-c22043af12ed",
    "locationId": "d6e32771-4733-4de5-9b95-d0ef1b30f00c",
    "billingPeriod": "Monthly",
    "paymentMethod": "CreditCard",
    "quantity": 1,
    "isAutoRenewed": true
}
```

We can deduce from this model an order of this type:

* Order of 1 product (4G Proxy)
* Located in Nice, France
* Paid Monthly
* With Credit Card
* With a subscription renewed every months



