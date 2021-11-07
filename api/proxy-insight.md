# Proxy Insight

## Introduction

`Proxy Insight` is one of the core features we are introducing in `HypeProxy.io v2.1` and it allows you to get a lot of information about your proxies and their uses.

Keep in mind that if we were to introduce new products that are not just proxies (like a VPN service for example) we will keep the term `Proxy Insight`.

## API Reference

Proxy Insight currently contains 4 endpoints, each rate limited to 1 call every 30 seconds.

### Ping a Proxy

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Insight/Ping/{productDetailsId}" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

### Get Remote IP Address

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Insight/Ip/{productDetailsId}" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

### Get IP Detailed Information

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Insight/IpDetails/{productDetailsId}" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

### Get IP Threats Information

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Insight/IpThreats/{productDetailsId}" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

