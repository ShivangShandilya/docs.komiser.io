---
slug: /cloud-providers/tencent
title: Tencent
sidebar_label: Tencent
---

# Tencent

## Supported resources
- Compute instances

## Local Komiser CLI (Single account)

Komiser now supports multiple cloud accounts by default. Account configuration is done through the `config.toml` file, just pass in your account `API Token`.

We've also added 2 methods of persisting your account data.
### Postgres
#### Add to config.toml file
```
[postgres]
uri="postgres://postgres:komiser@localhost:5432/komiser?sslmode=disable"
```
### SQLite

```
[sqlite]
  file = "komiser.db"
```

### Configuring Credentials

Firstly grab your Personal Access token from your Tencent account.

- Log in to the `CODING Console` and click `Use Now` to go to `CODING` page.
- Hover over your profile photo in the upper-right corner and click `Personal Settings`.
- In the menu on the left, click `Access Token.`
- Create an `access token`
- Click Create Token, enter a token description, and select the access permissions for the token.
- Click Create Token. When submitting the request, you will need to enter the service password to verify your identity.
- Click OK to create the access token.
- After submitting the request, you will be brought back to the list of access tokens, and the new token will be shown.

Need help finding it? Head on over to the official Tencent [documentation](https://www.tencentcloud.com/document/product/1132/44731).

### Add your Tencent Access token to your confuriation file

```
[[tencent]]
name="Staging-Account"
token="YOUR TOKEN"

[sqlite]
file="komiser.db
```
                                        

### Run it!
* That should be it. Try out the following from your command prompt to start the server:

```
komiser start 
```

* Point your browser to `http://localhost:3000`

## Local Komiser CLI (Multiple accounts)
Simply add more authentication blocks to the configuration file

```
[[tencent]]
name="Development-Account"
token="YOUR DEV ACOUNT TOKEN"

[[tencent]]
name="Staging-Account"
token="YOUR STAGING ACCOUNT TOKEN"

[[tencent]]
name="Production-Account"
token="YOUR PROD ACCOUNT TOKEN"

[sqlite]
file="komiser.db
```
