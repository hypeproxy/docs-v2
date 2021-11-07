# API Rate Limit

For obvious security reasons we prevent users to perform too many API requests and in this page we will list the different limitations.

The rate limit applies mainly to POST operations, GET endpoints are not limited.

## General Rules

```json
[
    {
        "Endpoint": "post:/v2/Authentication/SignUp",
        "Period": "1m",
        "Limit": 1
    },
    {
        "Endpoint": "post:/v2/Authentication/SignIn",
        "Period": "1m",
        "Limit": 5
    },
    {
        "Endpoint": "post:/v2/Orders/Validate",
        "Period": "1s",
        "Limit": 1
    },
    {
        "Endpoint": "post:/v2/Orders/Create",
        "Period": "15s",
        "Limit": 1
    },
    {
        "Endpoint": "post:/v2/Profile",
        "Period": "5s",
        "Limit": 1
    },
    {
        "Endpoint": "post:/v2/Tickets",
        "Period": "1m",
        "Limit": 1
    },
    {
        "Endpoint": "post:/v2/TicketAnswers/*",
        "Period": "1m",
        "Limit": 3
    },
    {
        "Endpoint": "post:/v2/Credentials/*",
        "Period": "1m",
        "Limit": 5
    },
    {
        "Endpoint": "post:/v2/Comments/*",
        "Period": "1m",
        "Limit": 5
    },
    {
        "Endpoint": "get:/v2/Renews/Execute/*",
        "Period": "30s",
        "Limit": 1
    },
    {
        "Endpoint": "get:/v2/Insight/*",
        "Period": "30s",
        "Limit": 1
    }
]
```
