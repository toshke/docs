
### Link Accounts

Call this endpoint to link the current user to an additional authentication method (e.g. user/password).


<aside class="notice">
For more information, see: <a href="/link-accounts">Linking Accounts</a>.
</aside>

This endpoint will trigger the login flow to link an existing account with a new one. This will return a 302 redirect to the `connection` that the current user wants to add. The user is identified by the `access_token` that was returned on login success.

#### Additional Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `access_token`   | object     | the logged-in user's access token |


## Access Token

Given the social provider's `access_token` and the `connection`, this endpoint will authenticate the user with the provider and return a JSON with the `access_token` and an `id_token`. This endpoint only works for Facebook, Google, Twitter and Weibo.

```shell
POST https://${account.namespace}/oauth/access_token
Content-Type: 'application/json'
{
  "client_id":    "{client_id}",
  "access_token": "",
  "connection":   "",
  "scope":        "",
  ""
}
```

```ruby
ruby
```

```python
python
```

```csharp
csharp
```

```php
php
```

```java
java
```

<aside class="notice">
For more information, see: <a href="/tokens/id_token">Auth0 id_token</a>.
</aside>

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

### HTTP Request

`POST https://${account.namespace}/oauth/access_token`

### Query Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `client_id`      | string     | the `client_id` of your app |
| `access_token`   | string     | the social provider's `access_token` |
| `connection`     | string     | the name of an identity provider configured to your app |
| `scope`          | string     | `openid` or `openid name email` |
