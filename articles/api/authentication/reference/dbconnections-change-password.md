---
title: Change Password
api_url: /dbconnections/change_password
api_method: POST
body_parameters:
  - name: client_id
    type: string
    description: "the `client_id` of your app"
  - name: email
    type: string
    description: "the user's email address"
  - name: connection
    type: string
    description: "the name of an identity provider configured to your app"
---

Given a user's `email` address and a `connection`, Auth0 will send a change password email.

```shell
POST https://${account.namespace}/dbconnections/change_password
Content-Type: 'application/json'
{
  "client_id":   "{client_id}",
  "email":       "",
  "password":    "",
  "connection":  "",
}
```

<aside class="notice">
For more information, see: <a href='/connections/database/password-change'>Changing a User's Password</a>.
</aside>

### Remarks

* If a password is provided, when the user clicks on the confirm password change link, the new password specified in this POST will be set for this user.
* If a password is NOT provided, when the user clicks on the password change link they will be redirected to a page asking them for a new password.
