# TokenInfo

<h5 class="code-snippet-title">Examples</h5>

```http
POST https://${account.namespace}/tokeninfo
Content-Type: 'application/json'
{
  "id_token": ""
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

This endpoint validates a JSON Web Token (signature and expiration) and returns the user information associated with the user id `sub` property of the token.

<aside class="notice">
For more information, see: <a href="/user-profile/user-profile-details#api">User Profile: In-Depth Details - API</a>.
</aside>

### HTTP Request

`POST https://${account.namespace}/tokeninfo`

### Query Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `id_token`       | object     |  |
