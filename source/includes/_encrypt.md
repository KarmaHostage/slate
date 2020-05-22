# Encryption

## Encrypt a string using a specific key

```http
POST https://api.karmahostage.com/encrypt
X-API-KEY: "sk_xxx"
{
  "plainText":"my secret text",
  "keyId":"e4dea538-37d3-40df-99a7-da9992d3300c"
}
```

```java
karmahostage.keys()
            .retrieve("e4dea538-37d3-40df-99a7-da9992d3300c")
            .encrypt("my secret text")
```

```shell
curl "http://api.karmahostage.com/encrypt"
  -H "X-API-KEY: sk_xxx"
  -x POST
  -d '{"keyId":"e4dea538-37d3-40df-99a7-da9992d3300c", "plainText":"my secret text"}'
```

> The above command returns JSON structured like this:

```json
{
  "cipherText":"vault:v1:VVDSf5jsM1xCtgQEjwq/i5+mIMRxVJe9BVOZCbG2p+U="
}
```

This endpoint will encrypt a string using the given cryptographic key. All work is done on Karmahostage servers. The key never leaves the servers during the process. Only metadata is fetched over the wire.
