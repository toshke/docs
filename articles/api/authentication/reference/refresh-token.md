## Offline Access (Refresh Tokens)

This endpoint will trigger the login flow to request a refresh token. This will return a 302 redirect to the `connection` specifying an extra scope (`offline_access`) and a `device` id that can be used to identify the refresh token in the dashboard. This extra scope will return the usual response plus a refresh token that can be used to obtain a new JSON Web Token. The refresh token can be [revoked](/api/management/v1#!#delete--api-users--user_id--refresh_tokens--refresh_token-)).


<aside class="notice">
For more information, see: <a href="/refresh-token">Refresh Tokens</a>.
</aside>

#### Additional Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `device`         | string     | an id for identifying the refresh token |
| `scope`          | string     | `openid offline_access` |
