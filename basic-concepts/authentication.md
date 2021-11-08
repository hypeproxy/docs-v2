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

{% swagger method="post" path="/v2/Authentication/SignIn" baseUrl="https://api.hypeproxy/io" summary="Login and Get JWT Token." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="email" type="String" required="true" %}
User email
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="String" required="true" %}
User password
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpCode" type="String" %}
User OTP, if you enabled 2FA
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Return your JWT Token (valid for 7 days)" %}
```javascript
"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="User doesn't exists." %}
```javascript
{
    "errors": "This user doesn't exists.",
    "message": "Request failed.",
    "statusCode": "BadRequest",
    "requestDetails": {
        "userId": "00000000-0000-0000-0000-000000000000",
        "endpoint": "/v2/Authentication/SignIn",
        "date": "2021-11-08T12:16:20.6210678Z",
        "timestamp": 1636373780,
        "userAgent": "PostmanRuntime/7.28.4",
        "clientIp": "::1"
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Incorrect password." %}
```javascript
{
    "message": "Incorrect password.",
    "statusCode": "Forbidden",
    "requestDetails": {
        "userId": "00000000-0000-0000-0000-000000000000",
        "endpoint": "/v2/Authentication/SignIn",
        "date": "2021-11-08T12:18:18.1897927Z",
        "timestamp": 1636373898,
        "userAgent": "PostmanRuntime/7.28.4",
        "clientIp": "::1"
    }
}
```
{% endswagger-response %}
{% endswagger %}
