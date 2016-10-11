# Authentication API: <br> Social Login with Web Applications

In this tutorial you will learn how to authenticate a user with their social connection (Facebook, Github, etc.) using Auth0. This document explains how to perform authentication using only the Auth0 Authentication API. Be sure to check out our [Quickstarts](/docs/quickstarts) and [Lock](/libraries/lock) for easier ways to perform authentication.

## Step 1: Redirect User to Authentication Endpoint
To start any social login process, we will need to redirect the user to the authentication endpoing.

```
https://${account.namespace}/authorize?
  response_type=code
  &client_id=${account.clientId}
  &connection=CONNECTION_NAME
  &redirect_uri=http://localhost:3000/callback
  &state=YOUR_STATE
```

| Parameter | Value     | Required | Description                                         |
|-----------|-----------|---------|------------------------------------------------------|
| `response_type` | `code` | Yes | for server side apps we use code |
| `client_id` | `YOUR_CLIENT_ID` | Yes | The client ID of the Auth0 client |
| `connection` | `CONNECTION_NAME` | Yes | The name of the connection. i.e. facebook, github, etc. |
| `redirect_uri` | `http://localhost:3000/callback` | Yes | The url of your app that will handle the auth response |
| `state` | `YOUR_STATE` | No | This is a value that returns to your app. See notes below. |

> Note: You can pass additional parameters as well by adding them to the query string. Some providers support additional parameters.

## Step 2: Auth0 Redirects to the Social Identity Provider
This step happens automatically for you, but it is included so you understand what is happening. When the authorize request comes into Auth0 we automatically translate that request to something that the identity provider can understand.

When the request is redirected to the identity provider the provider will display UI to login or authorize the request (in the case that the user is already authenticated to the provider).

This is where you would see something like the Facebook authorization dialog.
