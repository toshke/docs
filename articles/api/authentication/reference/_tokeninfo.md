# TokenInfo

This endpoint validates a JSON Web Token (signature and expiration) and returns the user information associated with the user id `sub` property of the token.

```shell
POST https://${account.namespace}/tokeninfo
Content-Type: 'application/json'
{
  "id_token": ""
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

`POST https://${account.namespace}/tokeninfo`

### Query Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `id_token`       | object     |  |
