# IP Rotation / Renewing

## Introduction

The IP renew feature is available on some types of proxies like 4G proxies, it's a very useful feature that many of our customers use.

{% hint style="success" %}
We are constantly improving this feature, we have reduced the renew speed of 4G proxies from more than 8 seconds to less than 5.
{% endhint %}

We currently support to kinds of IP rotation:

* [Automatic](ip-rotation.md#configure-automatic-rotation): Define an IP rotation every `X` minutes.
* [Manual](ip-rotation.md#execute-manual-rotation): Triggers a rotation at the time of the request.

## Configure Automatic Rotation

### Get the IP Renew

Get the renew parameters for a specific [product](../reference/productdetail.md).

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Renews/{productDetailsId}" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

### Set a IP Renew Delay

Define the delay of renew for a specific [product](../reference/productdetail.md), the minimum renew is 1 minute.

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Renews/{productDetailsId}" method="post" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

### Delete an IP Renew

Remove the IP renew feature for a specific [product](../reference/productdetail.md).

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Renews/{productDetailsId}" method="delete" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

## Execute Manual Rotation

The manual renew will be executed as an [asynchronous operation](../basic-concepts/asynchronous-operations.md), the API will return the related `requestId` of the operation.

So don't worry if the request delay is really fast, it's just because it's asynchronous, the renew will be performed in the background and takes about 5 to 8 seconds.

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Renews/Execute/{productDetailsId}" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}
