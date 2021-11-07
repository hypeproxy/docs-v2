# API Authentication

## How It Works?

The HypeProxy.io API requires an authentication token, but we were split between the demand of customers who didn't want to use a complex authentication mechanism like **JWT** and bringing a good level of security to our service, for this reason we decided to propose two mechanisms:

1. [Traditional JWT Authentication](authentication.md#traditional-jwt-authentication)
2. [Query Parameter Authentication](authentication.md#query-parameter-authentication)

## Traditional JWT Authentication

Here is a classic example of login with a JWT token, using the `Authorization` HTTP header:

```http
GET /v2/Profile HTTP/1.1
Host: api.hypeproxy.io
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

> The call of the `Profile` endpoint is just an example, it works same on every endpoints.

## Query Parameter Authentication

Some people can't make complex requests and/or don't have access to HTTP headers, so we accept the **JWT Token** as query parameter.

You just have to pass your JWT token as a `?apikey=` query string.

```bash
curl "https://api.hypeproxy.io/v2/Profile?apikey=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
```

## API Reference

### Sign In to API

To authenticate you need to use the endpoint `/v2/Authentication/SignIn`.

{% swagger src="../.gitbook/assets/swagger.json" path="undefined" method="undefined" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}
