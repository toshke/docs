# Unlink

```http
http
```

```shell
POST https://${account.namespace}/login/unlink?Content-Type: 'application/json'
{
  "access_token": "",
  "user_id":      ""
}
```

```javascript
javascript
```

> This command returns a JSON in this format:

```json
[
  {
    "id": 1
  },
  {
    "id": 2
  }
]
```

Given a logged-in user's `access_token` and `user_id`, this endpoint will unlink a user's account from identity provider .

<aside class="notice">
For more information, see: <a href="/link-accounts/auth-api#unlinking-accounts">Unlinking Accounts</a>.
</aside>

### HTTP Request

`POST https://${account.namespace}/unlink`

### Query Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `access_token`   | object     | the logged-in user's `access token` |
| `user_id`        | string     | the logged-in user's `user_id` |
