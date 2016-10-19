# Login

Redirect a user to the login page for the specified connection.

## Callback

This endpoint accepts an IdP-Initiated Sign On SAMLResponse from a SAML Identity Provider. The connection corresponding to the identity provider is specified in the querystring. The user will be redirected to the application that is specified in the SAML Provider IdP-Initiated Sign On section.

```shell
POST https://${account.namespace}/login/callback?connection=
Content-Type: 'application/x-www-form-urlencoded'

SAMLResponse=
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

`POST https://${account.namespace}/login/callback`

### Query Parameters

| Parameter        | Type       | Description |
|:-----------------|:-----------|:------------|
| `connection`     | string     | the name of an identity provider configured to your app |
| `SAMLResponse`   | string     | an IdP-Initiated Sign On SAML Response |