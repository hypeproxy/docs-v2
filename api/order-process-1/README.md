---
description: How order on HypeProxy.io using the API?
---

# Order Process

## Introduction

Our payment process is done in two steps, a first one of validation and a second one of creation.

## Structures

### Payment Methods

* CreditCard
* Cryptos

### Billing Period

* Monthly
* Weekly
* Daily
* Yearly



## Order Validation

```bash
curl --location --request POST 'https://api.hypeproxy.io/v2/Orders/Validate' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer API_TOKEN' \
--data-raw '{
    "productId": "7d8f2363-2fc9-47af-aae2-c22043af12ed",
    "locationId": "d6e32771-4733-4de5-9b95-d0ef1b30f00c",
    "billingPeriod": "Monthly",
    "paymentMethod": "CreditCard",
    "quantity": 1,
    "isAutoRenewed": false
}'
```

{% embed url="https://gist.github.com/clintnetwork/65a746d9c49f598d061ebaa4b47662fd" %}

{% content-ref url="order-validation.md" %}
[order-validation.md](order-validation.md)
{% endcontent-ref %}

{% content-ref url="order-creation.md" %}
[order-creation.md](order-creation.md)
{% endcontent-ref %}

## Order Validation

```
// Some code
```

