# V1 API Documentation

## Introduction

{% hint style="danger" %}
When we'll migrate to HypeProxy.io v2.1 this API will no longer be operational.
{% endhint %}

`HypeProxy.io v1 API` offers a JWT authentication, it's however possible to [renew the IP](v1-api-documentation.md#renew-ip) only with its proxy ID.

If you need more help with the API v1 please feel free to join our [live chat](https://go.crisp.chat/chat/embed/?website\_id=c96435ae-a92e-469f-b556-6befad2ff1d8).

## Retrieve your Proxy ID

First of all you have to connect to your dashboard, go to the section [4G / LTE Proxies](https://hypeproxy.io/dashboard/products/4g-proxies), then in the proxies list, you can see your IDs it's the sequence of alphanumeric characters with hash.

So for use the API you have to send the ID, following the screenshot below it's `00000000`.

![Dashboard Screenshot.](<../.gitbook/assets/Screenshot 2021-11-07 at 16.13.37.png>)

## API Reference

### Renew IP

{% swagger method="get" path="/Utils/DirectRenewIp/{id}" baseUrl="https://hypeproxy.io/api" summary="Renew the IP of a specific proxy [No Auth Required]" %}
{% swagger-description %}
This endpoint trigger the IP renew of the related proxy as an asynchronous operation, the process take around 8 seconds in background to be proceed and requires the reboot of the USB modem.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" required="true" type="" %}
Proxy ID, here to know how to get this ID.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="IP Renew Response." %}
```javascript
"IP Renew done."
```

Keep in mind that the operation is asynchronous, if the renew fail the api will always return the same response.
{% endswagger-response %}
{% endswagger %}

