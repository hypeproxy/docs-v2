# Asynchronous Operations

Some operations in our API are executed asynchronously, which means that you will not have to wait for the operation to finish.

In exchange, you will get a request ID that will allow you to consult the status of the operation via the call of another endpoint.

## Example of Response

This is an example of response from an asynchronous operation ([Manual IP Renew](../api-documentation/ip-rotation.md#execute-manual-rotation) in this case).

{% embed url="https://gist.github.com/clintnetwork/a84acbfdb84e9a9aaee9864f04ebbb14" %}
the field `requestId` in the `data` object can be used to retrieve the related operation.
{% endembed %}

## Retrieve an Operation with its ID

the field `requestId` in the `data` object can be used to retrieve the related operation

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Authentication/SignIn" method="post" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

## Endpoints Using Asynchronous Operations

There is a lit of endpoints using asynchronous operations:

* Manual IP Renew
* Test
