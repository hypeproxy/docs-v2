# Authentication

## Login and Get Authentication JWT token

{% swagger src="../.gitbook/assets/swagger.json" path="undefined" method="undefined" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

## Retrieve Your Token

There are two ways to get your JWT token as described bellow.

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
