---
title: Authorize
api_url: /authorize
api_method: GET
query_parameters:
  - name: response_type
    type: string
    description: "`code` (server-side) or `token` (client -side)"
  - name: client_id
    type: string
    description: "the `client_id` of your app"
  - name: connection
    type: string
    description: "the name of an identity provider configured to your app"
  - name: redirect_uri
    type: URL
    description: "the URL the user will be redirected to upon successful authentication"
  - name: state
    type: string
    description: "provided in the return"
---

Returns a redirect to the login page of the specified provider (passive authentication).

```shell
curl "GET http://${account.namespace}/api/authorize"
  -H "Authorization:"
```


<aside class="warning">
You must configure a <code>callback URL</code> in the management portal for your client application.
</aside>

### Remarks

* If no `connection` is specified, this will redirect to [Auth0 Login Page](${uiURL}/#/login_page) and show the Login widget using the first database connection.
* If `response_type=token`, after the user authenticates with the provider, this will redirect them to your application callback URL while passing the `access_token` and `id_token` in the address `location.hash`. This is used for Single Page Apps and on Native Mobile SDKs.
* Additional parameters can be sent that will be passed through to the provider, e.g. `access_type=offline` (for Google refresh tokens) , `display=popup` (for Windows Live popup mode).
* The `state` parameter will be returned and can be used for XSRF and contextual information (like a return url).


### Social Authentication

Use this endpoint to authenticate a user with a social provider. This endpoint will return a 302 redirect to the social provider specified in `connection`.

Social connections only support browser-based (passive) authentication because most social providers don't allow a username and password to be entered into applications that they don't own. Therefore, the user will be redirected to the provider's sign in page.

### Database & Active Directory / LDAP Authentication

This endpoint will return a 302 redirect to the [Auth0 Login Page](https://auth0.com/#/login_page) that will display the Lock widget where the user can login with their email and password. If you have multiple databases and Active Directory connections, use the  `connection` parameter to tell the widget which connection to use.

### Enterprise Authentication (SAML and Others)

This endpoint will return a 302 redirect to the enterprise provider specified in `connection`.
