# OAuth

Call these endpoints to generate access tokens.

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

## Resource Owner

Given the user's credentials, this endpoint will authenticate the user with the provider and return a JSON with the `access_token` and an `id_token`.

### HTTP Request

`POST https://${account.namespace}/oauth/ro`

### Database & Active Directory / LDAP Authentication

Login a user with username and password (active authentication).

```shell
POST https://${account.namespace}/oauth/ro
Content-Type: 'application/json'
{
  "client_id":   "{client_id}",
  "connection":  "",
  "grant_type":  "",
  "username":    "",
  "password":    "",
  "scope":       "",
  "id_token":    "",
  "device":      ""
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
This endpoint only works for database connections, passwordless connections, Active Directory/LDAP, Windows Azure AD and ADFS. For more information, see: <a href="/protocols#oauth-resource-owner-password-credentials-grant">OAuth Resource Owner Password Credentials Grant</a>.
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

### Query Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `client_id`      | string     | the `client_id` of your app |
| `connection`     | string     | the name of the AD connection configured to your app |
| `grant_type`     | string     | `password` |
| `username`       | string     | the user's username |
| `password`       | string     | the user's password |
| `scope`         | string     | `openid or openid name email or openid offline_access` |
| `id_token`       | string     |  |
| `device`         | string     |  |

### SMS

Login a user with their phone number and verification code (active authentication).

```shell
POST https://${account.namespace}/oauth/ro
Content-Type: 'application/json'
{
  "client_id":   "{client_id}",
  "connection":  "sms",
  "grant_type":  "password",
  "username":    "",
  "password":    "",
  "scope":       ""
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

### Query Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `client_id`      | string     | the `client_id` of your app |
| `connection`     | string     | `sms` |
| `grant_type`     | string     | `password` |
| `username`      | string     | the user's phone number |
| `password`      | string     | the user's verification code  |
| `scope`          | string     | `openid or openid name email` |

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
