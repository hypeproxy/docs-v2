# Getting Started

The `HypeProxy.io` API is organized around a [REST](https://en.wikipedia.org/wiki/Representational\_state\_transfer) architecture, all endpoints need to be [authenticated](authentication.md), and keep in mind that this documentation describes only the `v2` API.

Following the REST standard, you will often find a listing endpoint, an endpoint for retrieving a particular item, and sometimes a modification and/or deletion endpoint.

## How to connect to the API?

We provide two base URLs, we advise you to use the first one.

```bash
curl "https://api.hypeproxy.io/v2/"
curl "https://hypeproxy-api.azurewebsites.net/v2/"
```

## Authentication

Our API requires the use of a [JWT token](https://jwt.io/introduction) which can also be passed as a query string parameter.

{% content-ref url="authentication.md" %}
[authentication.md](authentication.md)
{% endcontent-ref %}

## Perform a Health Check

The API contains a health check endpoint that you can use if you have any impressions of failure.

The health check endpoint will also tell you if down bays have been detected.

```bash
curl "https://api.hypeproxy.io/health"
```

## Status Page

We have been offering a new status page for a few months now which is accessible [here](https://status.hypeproxy.io).

![HypeProxy.io Status Page Screenshot.](<../.gitbook/assets/Screenshot 2021-11-07 at 14.51.59.png>)

{% embed url="https://status.hypeproxy.io" %}

###
