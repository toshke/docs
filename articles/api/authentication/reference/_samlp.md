# SAMLP

The SAML protocol is mostly used for third-party SaaS applications (e.g. Salesforce, Box, etc.). Auth0 supports SP and IDP Initiated Sign On. 

```shell
GET https://${account.namespace}/{client_id}?connection=
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

### HTTP Request

`GET https://${account.namespace}/{client_id}`

### Query Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `client_id`      | string     | the `client_id` of your app |
| `connection`     | string     | the name of an identity provider configured to your app (optional, see remarks) |

<aside class="notice">
All the parameters of the SAML response can be modified with <a href='/rules'>rules </a>
</aside>

### Remarks

* This endpoint optionally accepts a `connection` parameter to login with the specified provider. If no connection is specified, the [Auth0 Login Page](/login_page) is shown.

* The SAML request `AssertionConsumerServiceURL` will be used to `POST` back the assertion. It must match the application's `callback_URL`.

## Metadata

This endpoint returns the SAML 2.0 metadata.

```shell
GET https://${account.namespace}/samlp/metadata/{client_id}
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

### HTTP Request

`GET https://${account.namespace}/samlp/metadata/`

### Query Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `client_id`      | string     | the `client_id` of your app |