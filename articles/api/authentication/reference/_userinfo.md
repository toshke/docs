# UserInfo

Given the Auth0 `access token` obtained during login, this endpoint returns a user's profile.

```shell
GET https://${account.namespace}/userinfo
Authorization: 'Bearer {access_token}'
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
For more information, see: <a href="/user-profile/user-profile-details#api">User Profile: In-Depth Details - API</a>.
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

`GET https://${account.namespace}/userinfo`

### Query Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `access_token`    | string     | the Auth0 `access_token` obtained during login |
