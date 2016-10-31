# UserInfo

<h5 class="code-snippet-title">Examples</h5>

```shell
shell
```

```http
GET https://${account.namespace}/userinfo
Authorization: 'Bearer {access_token}'
```

```javascript
javascript
```

> This command returns a JSON object in this format:

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

Given the Auth0 `access token` obtained during login, this endpoint returns a user's profile.

<aside class="notice">
For more information, see: <a href="/user-profile/user-profile-details#api">User Profile: In-Depth Details - API</a>.
</aside>

### HTTP Request

`GET https://${account.namespace}/userinfo`

### Query Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `access_token`    | string     | the Auth0 `access_token` obtained during login |
