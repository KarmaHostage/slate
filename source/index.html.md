---
title: Karmahostage API Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - http
  - java
  - shell

toc_footers:
  - <a href='https://developer.karmahostage.com'>Sign Up for a Developer Key</a>

includes:
  - keys
  - encrypt
  - decrypt
  - signatures
  - secrets
  - errors

search: true
---

# Introduction

Welcome to the Karmahostage EAAS API! 

You can use our API to access Karmahostage API endpoints, which allows you to perform cryptographic algorithms on data using your keys, securely stored on Karmahostage.

At this point, we don't have any libraries yet, but we're working on it! 
f
# Authentication

> To authorize, use this code:

```http
GET http://api.karmahostage.com/keys
X-API-KEY: sk_XXX
```

```java
Karmahostage karmahostage = 
    Karmahostage.builder()
                .apikey("sk_...")
                .build();
```

```shell
curl "https://api.karmahostage.com"
  -H "X-API-KEY: sk_xxx"
```


> Make sure to replace `sk_xxx` with the api key that you generated using https://dashboard.karmahostage.com

Karmahostage uses API keys to allow access to the API. You can register a application API key at our [developer portal](https://dashboard.karmahostage.com).

Karmahostage expects for the API key to be included in **all API requests** to the server in a header that looks like the following:

`X-API: sk_xxx`

<aside class="notice">
You must replace <code>sk_xxx</code> with your application API key.
</aside>
