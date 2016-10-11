
## Token

An `access_token` is required to call the Auth0 API. You can generate one by authenticating with your global `client_id` and `client_secret`. The token will be valid for 24 hours.

```shell
curl https://${account.namespace}/oauth/token --data "client_id=${account.clientId}&client_secret=${account.clientSecret}&type=web_server&grant_type=client_credentials"
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
For more information, see: <a href="/tokens/access_token">Auth0 access_token</a>.
</aside>

> This command returns a JSON with a body in this format:

```JSON
{
	"access_token":"TOKEN"
	"token_type":"bearer"
}
```

### HTTP Request

`POST https://${account.namespace}/oauth/token`

### Query Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `client_id`      | string     | your global `client_id` |
| `client_secret`  | string     | your global `client_secret` |
| `grant_type`     | string     | `client_credentials` |
| `type`     | string     | `web_server` (optional) |
| `audience`       | string     | the URL of your API endpoint (optional) |
