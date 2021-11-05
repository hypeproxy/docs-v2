---
description: HypeProxy.io API Authentication and Tokens.
---

# API Authentication

The HypeProxy.io API **requires authentication** for most endpoints, we use **JWT token** as authentication method, below is an example of a JWT token.

> eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV\_adQssw5c

## How to Use the Token?

We provide two ways of authentication, the normal JWT way and also `apikey` query parameter.

### As HTTP Header

The JWT normal way, as `Authorization` HTTP header.

```http
GET /v2/Profile HTTP/1.1
Host: api.hypeproxy.io
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

### As Query Parameter

Some people can't make complicated requests and/or don't have access to HTTP headers, so we accept the JWT token as query parameter like below.

```bash
curl "https://api.hypeproxy.io/v2/Profile?apikey=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
```

## Retrieve Your Token

There are two ways to get your JWT token as described bellow.

{% swagger baseUrl="https://api.hypeproxy.io" path="/v2/Authentication/SignIn" method="post" summary="Sign In to API" %}
{% swagger-description %}
Try to sign in to API and get JWT token or error response.
{% endswagger-description %}

{% swagger-parameter in="body" name="email" type="string" %}
Your email
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="string" %}
Your password
{% endswagger-parameter %}

{% swagger-response status="200" description="If you email is found and password is correct the response will only contains your JWT token." %}
```
"eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCJ9.eyJuYW1laWQiOiIzMjU3ZGU1NS01MDAxLTRmNmUtYjljZi02MzMyOGNkNjU0YjEiLCJ1bmlxdWVfbmFtZSI6Im1lQGNsaW50Lm5ldHdvcmsiLCJnaXZlbl9uYW1lIjoiQ2xpbnQgTW91cmxldmF0IiwiZW1haWwiOiJtZUBjbGludC5uZXR3b3JrIiwibmJmIjoxNjI1MTQ1Mzc5LCJleHAiOjE2MjU3NTAxNzksImlhdCI6MTYyNTE0NTM3OX0.poG6Ay4StGn9RjXgdhgl918qToqnA3LWZnU1EP1ggQujfMH0PN1aCqnzb1-y5LqROoz7YoTB0h3RofpFSNEyOA"
```
{% endswagger-response %}

{% swagger-response status="400" description="If your email doesn't exists in our database you will get this response." %}
```javascript
{
  "message": "This user doesn't exists.",
  "statusCode": "BadRequest",
  "requestDetails": {
    "userId": "00000000-0000-0000-0000-000000000000",
    "endpoint": "/v2/Authentication/SignIn",
    "date": "2021-07-01T13:19:11.024263Z",
    "timestamp": 1625145551,
    "userAgent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.114 Safari/537.36",
    "clientIp": "::1"
  }
}
```
{% endswagger-response %}

{% swagger-response status="403" description="If your password is incorrect you will get this response." %}
```javascript
{
  "message": "Incorrect password.",
  "statusCode": "Forbidden",
  "requestDetails": {
    "userId": "00000000-0000-0000-0000-000000000000",
    "endpoint": "/v2/Authentication/SignIn",
    "date": "2021-07-01T13:18:14.891394Z",
    "timestamp": 1625145494,
    "userAgent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.114 Safari/537.36",
    "clientIp": "::1"
  }
}
```
{% endswagger-response %}
{% endswagger %}

This is a small example of how to use the `SignIn` endpoint with cURL.

```bash
curl -X 'POST' \
  'https://api.hypeproxy.io/v2/Authentication/SignIn' \
  -d '{
  "email": "user@example.com",
  "password": "string"
}'
```

### Get Token From Your Profile

You need to log in to your account, click on your name in the top right corner, My Profile, API Key.

![](<../.gitbook/assets/Screenshot 2021-07-01 at 16.03.56.png>)

##
