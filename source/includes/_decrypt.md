# Decryption

## Decrypt an encrypted String using a specific key

```http
POST https://api.karmahostage.com/decrypt
X-API-KEY: "sk_xxx"
Content-Type: application/json

{
  "cipherText":"vault:v1:VVDSf5jsM1xCtgQEjwq/i5+mIMRxVJe9BVOZCbG2p+U=",
  "keyId":"e4dea538-37d3-40df-99a7-da9992d3300c"
}
```

```java
karmahostage.keys()
            .retrieve("e4dea538-37d3-40df-99a7-da9992d3300c")
            .decrypt("vault:v1:VVDSf5jsM1xCtgQEjwq/i5+mIMRxVJe9BVOZCbG2p+U=")
```

```shell
curl "http://api.karmahostage.com/decrypt"
  -H "X-API-KEY: sk_xxx"
  -H "Content-Type: application/json"  
  -x POST
  -d '{"keyId":"e4dea538-37d3-40df-99a7-da9992d3300c", "cipherText":"vault:v1:VVDSf5jsM1xCtgQEjwq/i5+mIMRxVJe9BVOZCbG2p+U="}'
```

> The above command returns JSON structured like this:

```json
{
  "plainText":"my secret text"
}
```

This endpoint will decrypt an encrypted string using the given cryptographic key. All work is done on Karmahostage servers. The key never leaves the servers during the process. Only metadata is fetched over the wire.
