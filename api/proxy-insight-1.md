# Proxy Insight

We have introduced in `HypeProxy.io v2.1` some new insights endpoints, that can give you many informations related to the IP address, threats or the network usage.

All these endpoints require the identifier of your product (called `productDetailsId`).

## Ping a Proxy

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Insight/Ping/{productDetailsId}" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

## Get Remote IP Address

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Insight/Ip/{productDetailsId}" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

## Get IP Detailed Information

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Insight/IpDetails/{productDetailsId}" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

## Get IP Threats Information

{% swagger src="../.gitbook/assets/swagger.json" path="/v2/Insight/IpThreats/{productDetailsId}" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

